# How to submit this entry to the Signalpost challenge

The agent code, the live smoke run, and the evidence are all done. The only
step left needs a human: sending one email.

## what to send

To: **submit@builderr.ai**
Subject: **Signalpost company research - entry submission**

Body (adjust the name/email to yours):

---

Hi,

Submitting my entry for the Signalpost company research challenge.

Agent code (single version): https://github.com/ssmurfgg04-gif/signalpost-agent
- fork of the reference starter with a recall-focused claims expansion:
  full registry fact set (industry code + label, business and postal address,
  municipality number, official website, latest submitted accounts,
  bankruptcy/liquidation status), uncapped role and subunit claims (was 12,
  now all active records, with subunit industry and employee counts), and
  company website URL + page title claims on top of description/social links
- bundled replay sample passes (recall 1.0, evidence complete, idempotent
  rerun), all 104 kit tests pass

Live 100-company smoke run on a clean GitHub-hosted runner (run
https://github.com/ssmurfgg04-gif/signalpost-agent/actions/runs/38896839650):
- 100/100 envelopes, zero silent drops, all entity and module states terminal
- 538 live requests, p95 688 ms, ~67 s wall clock for the batch
- report, profiles and envelopes archived as the run's artifact

I can supply a larger verified run (1,000+ companies) the same way if useful.

Name: <your name>
Email: <your email>

---

## before sending

- [ ] fill in your name and email in the body
- [ ] optionally re-run the smoke batch yourself: Actions tab -> smoke-batch
      -> Run workflow (the workflow reproduces everything: replay sample,
      tests, live 100-company batch)
- [ ] the deadline shown on the challenge page is Oct 21, 2026

## where things are

- agent: `src/norway_company_agent/` (recall changes are in `research.py`)
- runner workflow: `.github/workflows/smoke.yml`
- last verified smoke run: Actions run 38896839650, artifact `smoke-run`
  (contains `out/smoke-report.json`, `out/smoke-profiles.jsonl`,
  `out/smoke-envelopes.jsonl`, `entry-companies.jsonl`)
