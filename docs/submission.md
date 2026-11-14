# Drexathon submission: team CTM

**Title:** CTM: Drex checks every claim in a visa petition

**Track:** Apex Predator

## Explanation (for the form)

AI agents now draft founders' O-1A visa petitions. Each petition makes about 40 claims that its exhibits must
prove, and one unproven or contradicted claim triggers a USCIS Request for Evidence: months of delay. Today
a frontier model re-reads the whole case to judge each claim: slow, costly, run once at the end. CTM gives those
decisions to Drex. NDI turns exhibit PDFs into one shared state, and Drex judges eight claims per forward pass:
proven (with the exhibit), contradicted, or client-stated only. Code checks numbers; one threshold is fitted
on a dev split. As an Intern extension, CTM reopens the run so the agent fixes flagged claims before a
human sees them. The attorney then reads a 15-line receipt.

<!-- 120 words. No result numbers here; they are on the deck's results slides. -->

## Demo screen recording (60 to 90 seconds)

Synthetic demo case (`demo/case-demo`): fictional founder, fictional exhibits.

| Time | On screen | Voice-over |
|---|---|---|
| 0:00–0:08 | `demo/case-demo/exhibits/` in Finder or the terminal: offer letter, org chart, press | "This is a synthetic O-1A case: a founder and the exhibits that have to prove every claim in her petition." |
| 0:08–0:22 | Terminal: the `intern -p --system1 drex-latest --system2 deepinfra/Qwen/Qwen3.8-27B --extension ctm_drex.intern_ext:CtmReceipts ...` command from the README, then Intern streaming the draft | "Intern drafts the Critical Role and High Remuneration sections with Qwen on DeepInfra. CTM is loaded as an Intern extension." |
| 0:22–0:32 | The first draft open, the team-size and salary sentences highlighted | "Like most drafting agents, it overstates: a bigger team and a higher salary than the exhibits show." |
| 0:32–0:47 | `ctm-receipt.md`, first round: CONTRADICTED and CLIENT-STATED ONLY lines | "When the agent says it's done, Drex checks every sentence against the exhibits. Two claims fail, each with the exhibit and the reason. The number rule catches a figure the org chart never states." |
| 0:47–1:00 | Intern reopening the run with the receipt, then the revised sentences | "CTM reopens the run once and hands the agent the receipt. It rewrites only the flagged claims." |
| 1:00–1:12 | Second `ctm-receipt.md`: every line PROVEN with its exhibit | "The second draft passes. Every claim is proven, and every line names its exhibit." |
| 1:12–1:20 | Receipt beside the full draft and exhibit folder | "The attorney reads this 15-line receipt instead of the whole case. The frontier model writes; Drex checks every sentence as it's written." |

Recording notes: record at 1920×1080, terminal font 18 pt or larger, crop to the window. Run the case once
beforehand so both receipts exist, and cut the model's waiting time rather than speeding it up. State timings
only if they are on screen in the recording.
