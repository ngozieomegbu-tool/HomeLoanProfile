<!-- index.html -->
<!doctype html>
<html lang="en">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>Borrower Readiness Tool — Mortgage Readiness Snapshot</title>
  <meta name="description" content="A fast, pre-underwriting snapshot to help borrowers understand what a lender will need — not a loan approval." />
  <style>
    :root{
      --bg:#0b1020;
      --card:#0f172a;
      --text:#e5e7eb;
      --muted:#cbd5e1;
      --link:#60a5fa;
      --border:rgba(255,255,255,.12);
      --callout-bg:rgba(96,165,250,.14);
      --callout-border:rgba(96,165,250,.35);
    }
    *{box-sizing:border-box}
    body{
      margin:0;
      font-family: ui-sans-serif, system-ui, -apple-system, Segoe UI, Roboto, Helvetica, Arial, "Apple Color Emoji","Segoe UI Emoji";
      background: radial-gradient(1200px 600px at 20% -10%, rgba(96,165,250,.25), transparent 60%),
                  radial-gradient(900px 500px at 90% 10%, rgba(167,139,250,.18), transparent 55%),
                  var(--bg);
      color:var(--text);
      line-height:1.55;
    }
    .wrap{max-width:920px;margin:0 auto;padding:56px 20px}
    header h1{margin:0 0 8px;font-size:34px;letter-spacing:-.02em}
    header p{margin:0;color:var(--muted);max-width:70ch}
    .card{
      margin-top:22px;
      background:rgba(15,23,42,.88);
      border:1px solid var(--border);
      border-radius:16px;
      padding:20px;
      box-shadow: 0 10px 30px rgba(0,0,0,.25);
      backdrop-filter: blur(6px);
    }
    .callout{
      display:flex; gap:12px; align-items:flex-start;
      background:var(--callout-bg);
      border:1px solid var(--callout-border);
      border-radius:14px;
      padding:14px 14px;
      margin: 18px 0 20px;
    }
    .callout .icon{font-size:18px;line-height:1.2;margin-top:1px}
    h2{margin:22px 0 10px;font-size:20px}
    h3{margin:18px 0 8px;font-size:16px}
    ul{margin:8px 0 0 20px;color:var(--muted)}
    ol{margin:8px 0 0 20px;color:var(--muted)}
    a{color:var(--link);text-decoration:none}
    a:hover{text-decoration:underline}
    hr{border:0;border-top:1px solid var(--border);margin:22px 0}
    footer{margin-top:18px;color:var(--muted);font-size:13px}
    .btn{
      display:inline-flex;align-items:center;gap:10px;
      background:#2563eb;color:#fff;
      padding:12px 14px;border-radius:12px;
      border:1px solid rgba(255,255,255,.12);
      text-decoration:none;font-weight:600;
      margin-top:10px;
    }
    .btn:focus,.btn:hover{filter:brightness(1.06);text-decoration:none}
    .small{font-size:14px;color:var(--muted)}
  </style>
</head>

<body>
  <div class="wrap">
    <header>
      <h1>Borrower Readiness Tool — Mortgage Readiness Snapshot</h1>
      <p>A fast, pre-underwriting snapshot to help borrowers understand what a lender will need — <em>not a loan approval</em>.</p>
    </header>

    <main class="card">
      <div class="callout" role="note" aria-label="Info">
        <div class="icon">ℹ️</div>
        <div>
          A fast, pre-underwriting snapshot to help borrowers understand what a lender will need — <em>not a loan approval</em>.
        </div>
      </div>

      <h2>Get your Mortgage Readiness Summary</h2>
      <p class="small">Use the tool here:</p>
      <a class="btn" href="https://ngozieomegbu-tool.github.io/HomeLoanProfile/" target="_blank" rel="noopener">
        Open Borrower Profile Tool
        <span aria-hidden="true">↗</span>
      </a>

      <h2>What you’ll get</h2>
      <ul>
        <li>Borrower profile snapshot (occupancy, borrower type, eligibility flags)</li>
        <li>Income &amp; capacity estimate (DTI, estimated loan amount, purchase power)</li>
        <li>Cash-to-close estimate</li>
        <li>Document checklist tailored to the scenario</li>
        <li>Investor / rental analysis (DSCR)</li>
        <li>Loan payment preview (rate, term, monthly payment)</li>
      </ul>

      <h2>Common flags the tool can identify</h2>
      <ul>
        <li>Foreign national (limited programs)</li>
        <li>Expired/invalid ID (must renew before closing)</li>
        <li>No score / locked credit file (manual review needed)</li>
        <li>Interested party contribution ≥ 25% (additional documentation)</li>
        <li>Gift funds only (helps assets, not income)</li>
        <li>Multiple properties owned (REO schedule required)</li>
      </ul>

      <h2>Documents you may need (examples)</h2>
      <ul>
        <li>Government-issued photo ID</li>
        <li>Income documentation (or paid verification)</li>
        <li>2 months most recent bank statements</li>
        <li>Verification of assets (401(k), IRA)</li>
        <li>REO schedule (all owned properties)</li>
        <li>Gift letter + donor bank statement</li>
      </ul>

      <h2>Next steps</h2>
      <ol>
        <li>Complete the tool and save your summary.</li>
        <li>Gather the items in the document checklist.</li>
        <li>Share the summary with your mortgage professional for a full review.</li>
      </ol>

      <hr />

      <h3>Important disclaimer</h3>
      <p class="small">
        This is a pre-underwriting screening tool for informational purposes only and does not constitute a loan
        commitment, approval, or guarantee of financing. All figures are estimates. Final loan eligibility is subject to full
        underwriting, lender guidelines, property appraisal, and applicable law. Consult a licensed mortgage professional
        before making financial decisions.
      </p>

      <footer>
        Prepared by: Ngozie Omegbu, NMLS ID #2077106 (WI / nationwide referrals)<br />
        Date: April 21, 2026
      </footer>
    </main>
  </div>
</body>
</html>
