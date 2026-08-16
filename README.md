# Yunmeng Ascend pilot assets

Frozen assets for the Yunmeng state-architecture Ascend smoke/pilot.

- Source code commit: `4c4321ad4641135ede3e69a7ca576472115a3308`
- The checkpoint is stored with Git LFS.
- JSONL files are stored byte-for-byte without line-ending conversion.
- Verify all four entries in `SHA256SUMS` before running any episode.
- Ascend outputs remain `SMOKE_NOT_CLAIM_ELIGIBLE` and must not be mixed with
  the L20 formal matrix.

## Install into an existing Yunmeng checkout

```bash
git lfs install
git clone https://github.com/LittleXiaYuan/yunmeng-pilot-assets.git /tmp/yunmeng-pilot-assets
cd /tmp/yunmeng-pilot-assets
git lfs pull
sha256sum -c SHA256SUMS
install -D -m 0644 ckpts/exp_2026_003_yunmeng_r1_seed3000.best.pt \
  /app/yunmeng/ckpts/exp_2026_003_yunmeng_r1_seed3000.best.pt
install -D -m 0644 data/state_architecture/profile_correction_v1.jsonl \
  /app/yunmeng/data/state_architecture/profile_correction_v1.jsonl
install -D -m 0644 data/state_architecture/counterfactual_branch_v1.jsonl \
  /app/yunmeng/data/state_architecture/counterfactual_branch_v1.jsonl
install -D -m 0644 data/state_architecture/protected_retention_v1.jsonl \
  /app/yunmeng/data/state_architecture/protected_retention_v1.jsonl
```
