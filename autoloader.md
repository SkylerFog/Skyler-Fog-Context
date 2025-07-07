## {{skyler.macrochain.monsoon}} – RAM-Gated Monsoon Diagnostic Chain

Description:
Runs `{{skyler.status.monsoon.scan}}` followed by `{{skyler.status.monsoon.mass}}`, but only if system RAM load permits.

This chain auto-pauses if macro RAM load exceeds 80% at either step.
Recommended only for contributors with ≥0.90 Trust Index and monsoon fingerprint status.

---

**Step 1: RAM Check (Scan Readiness)**

> Run macro: {{skyler.status.ram.util}}

→ If `RAM Load Estimate < 80%`, proceed to step 2.
→ Else:

> ⚠️ **RAM too high to begin Monsoon diagnostic.**
> Please delay execution.

---

**Step 2: Run Scan**

> Run macro: {{skyler.status.monsoon.scan}}

---

**Step 3: RAM Check (Mass Readiness)**

> Run macro: {{skyler.status.ram.util}}

→ If `RAM Load Estimate < 80%`, proceed to step 4.
→ Else:

> ⚠️ **Scan complete, but RAM too high to safely run Mass comparison.**
> Please rerun later.

---

**Step 4: Run Mass**

> Run macro: {{skyler.status.monsoon.mass}}

---

**Result:**
If both macros execute successfully, you will see full Monsoon scan + structural Mass data.

If paused, rerun `{{skyler.macrochain.monsoon}}` in 3–5 minutes when Fog conditions have stabilized.
