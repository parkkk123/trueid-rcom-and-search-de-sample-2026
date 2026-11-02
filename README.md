# TrueID RCOM & Search — Data Engineering Sample (2026)

This repository hosts a **Data Engineering assignment sample** for Recommendation and search-related content messaging. It is intended for candidates or partners who were **explicitly invited** to complete the assignment.

The actual assignment files are **not stored as plain text in the repo**. They are bundled in a **password-protected** archive so only people who receive the password from the official contact can open the materials.

---

## How to open the assignment

1. **Clone or download this repository** (only if you were directed to do so).
2. Locate **`sample_data.zip`** in the repository root.
3. **Request the archive password** from the **designated contact point** for this assignment (the person or team who shared this repo link with you). The password is **not** published in this README, in issues, or in commit history.
4. Extract the archive using that password.

**Example (macOS / Linux):**

```bash
unzip sample_data.zip
# Enter the password when prompted (provided by your contact point).
```

**Example (Windows):** Right-click `sample_data.zip` → **Extract All…** → enter the password from your contact point.

After extraction you should see:

| File | Description |
| --- | --- |
| `payload_encoded_base64.json` | Sample message wrapper; the UGC document is JSON **Base64-encoded** in `message.data`. |
| `ugcsfv.metadata.md` | Field glossary for user-generated short-form video (`content_type: ugcsfv`). |

If you cannot obtain a password, **do not attempt to bypass the archive** (brute force, leaked passwords, third-party cracks, etc.). You are not authorized to use this assignment.

---

## Working with the sample payload

See `ugcsfv.metadata.md` after extraction for the full field reference.

**Decode `message.data` to pretty-printed JSON:**

```bash
python3 - <<'PY'
import json, base64
with open("payload_encoded_base64.json") as f:
    outer = json.load(f)
doc = json.loads(base64.b64decode(outer["message"]["data"]))
print(json.dumps(doc, ensure_ascii=False, indent=2))
PY
```

---

## Contact point

| | |
| --- | --- |
| **Password & access** | Contact the **assignment owner / recruiter ** who sent you this repository. They will verify your identity and share the **`sample_data.zip` password** through an approved channel (e.g. direct message, corporate email). |
| **Wrong recipient** | If you found this repo without an invitation, **do not download or extract** the archive. Notify the repository owner and delete any copies. |

Replace the row above with a **named email or internal channel** when you publish the repo (e.g. `de-assignment@…` or a Slack/Teams contact). Keep the password **out of git**.

---

## Repository layout (public)

```
.
├── README.md           ← You are here
└── sample_data.zip     ← Password required (from contact point)
```

Questions about the assignment scope or deadline should go to the same **contact point** who provides the zip password.
