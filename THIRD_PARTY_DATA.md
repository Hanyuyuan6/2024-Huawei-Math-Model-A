# Third-party competition data

## Source and redistribution boundary

The official 2024 competition notice instructed registered participants to obtain the problem download link through the competition system and allowed participants to share the link or downloaded problem files during the event:

- https://cpipc.acge.org.cn/cw/contestNews/detail/4/2c90801592055ef701920a05d54e1fd2

That notice does not state a durable open-data license for public redistribution. Therefore this repository does not distribute the problem statement, official attachments, raw datasets, or submission templates and does not grant rights to them. Obtain the materials from the organizer and comply with the organizer's current terms.

## Expected local files

Place authorized local copies in `Math_Model/`. These paths are ignored by Git.

| File | Role | SHA-256 of the copy removed from `main` on 2026-08-02 |
|---|---|---|
| `附件1-疲劳评估数据.xls` | Question 1 input | `e3112e08012a08a78439f16c82bc7c1c8bcd29cae4878a772ebf06679fbf25c3` |
| `附件2-风电机组采集数据.mat` | Questions 2-4 input | `68406f58ccbb3ebd70f704ffb45b7a1bfc899c6512228994f4f1d725fe2fbd1b` |
| `附件3-噪声和延迟作用下的采集数据.mat` | Question 4 input | `b2c61a007b3085451d0c420e16a0c80b806a2d5e89a4cdd008cce71fd57a60df` |
| `附件4-噪声和延迟作用下的采集数据.xlsx` | Question 4 test input | `c0f5691a6b7ff8dcdbeda84b8a0bd8adc5bebd9e44003751bdc482f7d27b092e` |

The hashes identify the exact local copies used by the released code; they are not a substitute for provenance or permission. A different authorized copy may legitimately have a different hash because of packaging or Office metadata.

## Verify a local copy

Windows PowerShell:

```powershell
Get-FileHash -Algorithm SHA256 -LiteralPath '.\Math_Model\附件2-风电机组采集数据.mat'
```

macOS/Linux:

```bash
shasum -a 256 'Math_Model/附件2-风电机组采集数据.mat'
```

Do not commit answer sheets, raw competition attachments, credentials, or machine-local Office metadata.
