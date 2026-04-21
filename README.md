[index (1).html](https://github.com/user-attachments/files/26949676/index.1.html)
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8"/>
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Borrower Readiness Tool — Mortgage Readiness Snapshot</title>
  <link href="https://fonts.googleapis.com/css2?family=Cormorant+Garamond:ital,wght@0,300;0,400;0,600;1,300;1,400&family=DM+Sans:wght@300;400;500&display=swap" rel="stylesheet"/>
  <style>
    *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

    :root {
      --navy:        #0d1b2a;
      --navy-mid:    #162a40;
      --gold:        #c9a84c;
      --gold-light:  #e8c96a;
      --gold-pale:   rgba(201,168,76,0.12);
      --cream:       #f7f3ec;
      --cream-deep:  #efe9de;
      --muted:       #8a8070;
      --border:      #d9d0c0;
      --white:       #ffffff;
    }

    html { scroll-behavior: smooth; }

    body {
      font-family: 'DM Sans', sans-serif;
      background: var(--navy);
      color: var(--cream);
      overflow-x: hidden;
    }

    /* ── NOISE OVERLAY ── */
    body::before {
      content: '';
      position: fixed; inset: 0;
      background-image: url("data:image/svg+xml,%3Csvg viewBox='0 0 200 200' xmlns='http://www.w3.org/2000/svg'%3E%3Cfilter id='n'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='0.9' numOctaves='4' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='100%25' height='100%25' filter='url(%23n)' opacity='0.04'/%3E%3C/svg%3E");
      pointer-events: none; z-index: 0; opacity: 0.4;
    }

    /* ── HERO ── */
    .hero {
      position: relative;
      min-height: 100vh;
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      padding: 6rem 2rem 5rem;
      text-align: center;
      overflow: hidden;
    }

    /* radial glow */
    .hero::after {
      content: '';
      position: absolute;
      top: -10%; left: 50%;
      transform: translateX(-50%);
      width: 700px; height: 700px;
      background: radial-gradient(ellipse, rgba(201,168,76,0.13) 0%, transparent 70%);
      pointer-events: none;
    }

    /* animated grid lines */
    .grid-lines {
      position: absolute; inset: 0;
      background-image:
        linear-gradient(rgba(201,168,76,0.04) 1px, transparent 1px),
        linear-gradient(90deg, rgba(201,168,76,0.04) 1px, transparent 1px);
      background-size: 60px 60px;
      animation: gridDrift 30s linear infinite;
      pointer-events: none;
    }
    @keyframes gridDrift {
      from { background-position: 0 0; }
      to   { background-position: 60px 60px; }
    }

    .hero-content { position: relative; z-index: 1; max-width: 760px; }

    .eyebrow {
      display: inline-flex;
      align-items: center;
      gap: 0.6rem;
      font-size: 0.7rem;
      font-weight: 500;
      letter-spacing: 0.22em;
      text-transform: uppercase;
      color: var(--gold);
      margin-bottom: 1.6rem;
      animation: fadeUp 0.7s 0.1s both;
    }
    .eyebrow::before, .eyebrow::after {
      content: '';
      display: block;
      width: 28px; height: 1px;
      background: var(--gold);
      opacity: 0.5;
    }

    h1 {
      font-family: 'Cormorant Garamond', serif;
      font-size: clamp(2.8rem, 6vw, 5rem);
      font-weight: 300;
      line-height: 1.08;
      letter-spacing: -0.02em;
      color: var(--cream);
      margin-bottom: 0.3em;
      animation: fadeUp 0.7s 0.2s both;
    }
    h1 em {
      font-style: italic;
      color: var(--gold-light);
    }

    .hero-sub {
      font-size: 1rem;
      font-weight: 300;
      color: rgba(247,243,236,0.65);
      max-width: 500px;
      margin: 0 auto 2.8rem;
      line-height: 1.65;
      animation: fadeUp 0.7s 0.3s both;
    }

    .disclaimer-pill {
      display: inline-block;
      padding: 0.35rem 1rem;
      border: 1px solid rgba(201,168,76,0.3);
      border-radius: 100px;
      font-size: 0.72rem;
      color: rgba(201,168,76,0.7);
      letter-spacing: 0.06em;
      margin-bottom: 2.8rem;
      animation: fadeUp 0.7s 0.35s both;
    }

    .cta-group {
      display: flex;
      flex-wrap: wrap;
      gap: 1rem;
      justify-content: center;
      animation: fadeUp 0.7s 0.45s both;
    }

    .btn-primary {
      padding: 0.9rem 2.2rem;
      background: var(--gold);
      color: var(--navy);
      border: none;
      border-radius: 1px;
      font-family: 'DM Sans', sans-serif;
      font-size: 0.78rem;
      font-weight: 500;
      letter-spacing: 0.16em;
      text-transform: uppercase;
      text-decoration: none;
      cursor: pointer;
      transition: background 0.2s, transform 0.15s, box-shadow 0.2s;
      box-shadow: 0 4px 24px rgba(201,168,76,0.25);
    }
    .btn-primary:hover {
      background: var(--gold-light);
      transform: translateY(-1px);
      box-shadow: 0 8px 32px rgba(201,168,76,0.35);
    }

    .btn-secondary {
      padding: 0.9rem 2.2rem;
      background: transparent;
      color: var(--cream);
      border: 1px solid rgba(247,243,236,0.25);
      border-radius: 1px;
      font-family: 'DM Sans', sans-serif;
      font-size: 0.78rem;
      font-weight: 400;
      letter-spacing: 0.16em;
      text-transform: uppercase;
      text-decoration: none;
      cursor: pointer;
      transition: border-color 0.2s, color 0.2s;
    }
    .btn-secondary:hover {
      border-color: var(--gold);
      color: var(--gold-light);
    }

    /* ── SCROLL INDICATOR ── */
    .scroll-hint {
      position: absolute;
      bottom: 2.5rem; left: 50%;
      transform: translateX(-50%);
      display: flex; flex-direction: column; align-items: center; gap: 0.4rem;
      opacity: 0.4; font-size: 0.65rem; letter-spacing: 0.15em; text-transform: uppercase;
      animation: fadeUp 1s 1s both;
    }
    .scroll-hint .line {
      width: 1px; height: 36px;
      background: linear-gradient(to bottom, var(--gold), transparent);
      animation: scrollPulse 1.8s ease-in-out infinite;
    }
    @keyframes scrollPulse {
      0%, 100% { opacity: 0.3; transform: scaleY(1); }
      50%       { opacity: 0.8; transform: scaleY(1.1); }
    }

    /* ── SECTIONS ── */
    section { position: relative; z-index: 1; }

    .section-inner {
      max-width: 960px;
      margin: 0 auto;
      padding: 5rem 2rem;
    }

    .section-label {
      font-size: 0.68rem;
      font-weight: 500;
      letter-spacing: 0.22em;
      text-transform: uppercase;
      color: var(--gold);
      margin-bottom: 1rem;
    }

    .section-title {
      font-family: 'Cormorant Garamond', serif;
      font-size: clamp(1.8rem, 3.5vw, 2.8rem);
      font-weight: 300;
      color: var(--cream);
      line-height: 1.15;
      margin-bottom: 1.2rem;
    }

    .section-body {
      font-size: 0.9rem;
      font-weight: 300;
      color: rgba(247,243,236,0.6);
      line-height: 1.75;
      max-width: 560px;
    }

    /* gold rule */
    .gold-rule {
      width: 40px; height: 1px;
      background: var(--gold);
      margin: 1.4rem 0;
    }

    /* ── WHAT YOU'LL GET ── */
    .gets-section { background: rgba(255,255,255,0.02); border-top: 1px solid rgba(201,168,76,0.1); border-bottom: 1px solid rgba(201,168,76,0.1); }

    .gets-grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(240px, 1fr));
      gap: 1px;
      margin-top: 3rem;
      border: 1px solid rgba(201,168,76,0.12);
    }

    .get-item {
      padding: 2rem 1.8rem;
      border-right: 1px solid rgba(201,168,76,0.12);
      transition: background 0.25s;
      opacity: 0;
      transform: translateY(16px);
      transition: opacity 0.5s ease, transform 0.5s ease, background 0.25s;
    }
    .get-item.visible { opacity: 1; transform: translateY(0); }
    .get-item:hover { background: rgba(201,168,76,0.04); }
    .get-item:last-child { border-right: none; }

    .get-icon {
      font-size: 1.3rem;
      margin-bottom: 0.8rem;
      color: var(--gold);
    }

    .get-title {
      font-family: 'Cormorant Garamond', serif;
      font-size: 1.05rem;
      font-weight: 400;
      color: var(--cream);
      margin-bottom: 0.4rem;
    }

    .get-desc {
      font-size: 0.78rem;
      font-weight: 300;
      color: rgba(247,243,236,0.5);
      line-height: 1.6;
    }

    /* ── FLAGS ── */
    .flags-section { }

    .flags-layout {
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 4rem;
      align-items: start;
      margin-top: 1rem;
    }

    .flag-list {
      list-style: none;
      margin-top: 2rem;
      display: flex;
      flex-direction: column;
      gap: 0.75rem;
    }

    .flag-list li {
      display: flex;
      align-items: flex-start;
      gap: 0.8rem;
      font-size: 0.85rem;
      font-weight: 300;
      color: rgba(247,243,236,0.7);
      line-height: 1.5;
      opacity: 0;
      transform: translateX(-10px);
      transition: opacity 0.4s ease, transform 0.4s ease;
    }
    .flag-list li.visible { opacity: 1; transform: translateX(0); }

    .flag-list li::before {
      content: '◆';
      color: var(--gold);
      font-size: 0.4rem;
      margin-top: 0.45rem;
      flex-shrink: 0;
    }

    /* ── DOCUMENTS ── */
    .docs-box {
      border: 1px solid rgba(201,168,76,0.18);
      padding: 2.5rem;
      margin-top: 2rem;
      position: relative;
    }
    .docs-box::before {
      content: 'Documents You May Need';
      position: absolute;
      top: -0.65rem; left: 1.5rem;
      background: var(--navy);
      padding: 0 0.6rem;
      font-size: 0.68rem;
      letter-spacing: 0.18em;
      text-transform: uppercase;
      color: var(--gold);
    }

    .doc-chips {
      display: flex;
      flex-wrap: wrap;
      gap: 0.6rem;
      margin-top: 0.5rem;
    }

    .chip {
      padding: 0.4rem 0.9rem;
      border: 1px solid rgba(201,168,76,0.2);
      font-size: 0.76rem;
      font-weight: 300;
      color: rgba(247,243,236,0.7);
      letter-spacing: 0.04em;
      border-radius: 1px;
      transition: border-color 0.2s, color 0.2s;
    }
    .chip:hover { border-color: var(--gold); color: var(--gold-light); }

    /* ── STEPS ── */
    .steps-section { background: rgba(255,255,255,0.015); border-top: 1px solid rgba(201,168,76,0.08); }

    .steps-track {
      display: grid;
      grid-template-columns: repeat(3, 1fr);
      gap: 0;
      margin-top: 3rem;
      position: relative;
    }

    .steps-track::before {
      content: '';
      position: absolute;
      top: 1.6rem; left: 8%; right: 8%;
      height: 1px;
      background: linear-gradient(90deg, transparent, var(--gold), transparent);
      opacity: 0.3;
    }

    .step {
      text-align: center;
      padding: 0 1.5rem;
      opacity: 0;
      transform: translateY(20px);
      transition: opacity 0.5s ease, transform 0.5s ease;
    }
    .step.visible { opacity: 1; transform: translateY(0); }

    .step-num {
      width: 3.2rem; height: 3.2rem;
      border: 1px solid rgba(201,168,76,0.4);
      border-radius: 50%;
      display: flex; align-items: center; justify-content: center;
      margin: 0 auto 1.2rem;
      font-family: 'Cormorant Garamond', serif;
      font-size: 1.1rem;
      color: var(--gold);
      background: var(--navy);
      position: relative; z-index: 1;
    }

    .step-title {
      font-family: 'Cormorant Garamond', serif;
      font-size: 1.05rem;
      font-weight: 400;
      color: var(--cream);
      margin-bottom: 0.5rem;
    }

    .step-desc {
      font-size: 0.78rem;
      font-weight: 300;
      color: rgba(247,243,236,0.5);
      line-height: 1.6;
    }

    /* ── CTA BAND ── */
    .cta-band {
      text-align: center;
      padding: 6rem 2rem;
      background: linear-gradient(135deg, rgba(201,168,76,0.06) 0%, transparent 60%);
      border-top: 1px solid rgba(201,168,76,0.12);
    }

    .cta-band h2 {
      font-family: 'Cormorant Garamond', serif;
      font-size: clamp(2rem, 4vw, 3.2rem);
      font-weight: 300;
      color: var(--cream);
      margin-bottom: 0.6rem;
    }

    .cta-band p {
      font-size: 0.88rem;
      font-weight: 300;
      color: rgba(247,243,236,0.5);
      margin-bottom: 2.5rem;
    }

    /* ── FOOTER ── */
    footer {
      border-top: 1px solid rgba(201,168,76,0.1);
      padding: 2.5rem 2rem;
      text-align: center;
    }

    .footer-brand {
      font-family: 'Cormorant Garamond', serif;
      font-size: 1rem;
      color: var(--gold);
      letter-spacing: 0.08em;
      margin-bottom: 0.5rem;
    }

    .footer-legal {
      font-size: 0.72rem;
      font-weight: 300;
      color: rgba(247,243,236,0.3);
      max-width: 600px;
      margin: 0 auto;
      line-height: 1.65;
    }

    /* ── ANIMATIONS ── */
    @keyframes fadeUp {
      from { opacity: 0; transform: translateY(18px); }
      to   { opacity: 1; transform: translateY(0); }
    }

    /* ── RESPONSIVE ── */
    @media (max-width: 700px) {
      .flags-layout { grid-template-columns: 1fr; gap: 2rem; }
      .steps-track  { grid-template-columns: 1fr; gap: 2rem; }
      .steps-track::before { display: none; }
      .gets-grid { grid-template-columns: 1fr; }
      .get-item { border-right: none; border-bottom: 1px solid rgba(201,168,76,0.12); }
    }
  </style>
</head>
<body>

  <!-- HERO -->
  <section class="hero">
    <div class="grid-lines"></div>
    <div class="hero-content">
      <div class="eyebrow">NEXA Lending · Ngozie Omegbu NMLS #2077106</div>
      <h1>Mortgage Readiness<br/><em>Snapshot</em></h1>
      <p class="hero-sub">A fast, pre-underwriting snapshot to help you understand what a lender will need — before you sit down at the table.</p>
      <div class="disclaimer-pill">Not a loan approval · Informational purposes only</div>
      <div class="cta-group">
        <a href="https://ngozieomegbu-tool.github.io/HomeLoanProfile/" target="_blank" class="btn-primary">Get My Readiness Summary</a>
        <a href="#steps" class="btn-secondary">How It Works</a>
      </div>
    </div>
    <div class="scroll-hint"><span class="line"></span>Scroll</div>
  </section>

  <!-- WHAT YOU'LL GET -->
  <section class="gets-section">
    <div class="section-inner">
      <div class="section-label">What You'll Receive</div>
      <h2 class="section-title">Everything you need to walk in<br/>prepared and confident.</h2>
      <div class="gold-rule"></div>
      <div class="gets-grid">
        <div class="get-item">
          <div class="get-icon">◈</div>
          <div class="get-title">Borrower Profile Snapshot</div>
          <div class="get-desc">Occupancy type, borrower classification, and eligibility flags identified upfront.</div>
        </div>
        <div class="get-item">
          <div class="get-icon">◈</div>
          <div class="get-title">Income & Capacity Estimate</div>
          <div class="get-desc">DTI ratio, estimated loan amount, and purchase power based on your inputs.</div>
        </div>
        <div class="get-item">
          <div class="get-icon">◈</div>
          <div class="get-title">Cash-to-Close Estimate</div>
          <div class="get-desc">Projected funds needed at closing so there are no surprises on closing day.</div>
        </div>
        <div class="get-item">
          <div class="get-icon">◈</div>
          <div class="get-title">Document Checklist</div>
          <div class="get-desc">A tailored list of documents required for your specific loan scenario.</div>
        </div>
        <div class="get-item">
          <div class="get-icon">◈</div>
          <div class="get-title">Investor / DSCR Analysis</div>
          <div class="get-desc">Debt service coverage ratio analysis for investment and rental property buyers.</div>
        </div>
        <div class="get-item">
          <div class="get-icon">◈</div>
          <div class="get-title">Loan Payment Preview</div>
          <div class="get-desc">Estimated rate, term, and monthly payment so you can plan with clarity.</div>
        </div>
      </div>
    </div>
  </section>

  <!-- FLAGS + DOCUMENTS -->
  <section class="flags-section">
    <div class="section-inner">
      <div class="flags-layout">
        <div>
          <div class="section-label">Common Flags Identified</div>
          <h2 class="section-title">Know your position<br/>before you apply.</h2>
          <div class="gold-rule"></div>
          <p class="section-body">The tool surfaces issues lenders will scrutinize — so you can address them ahead of time rather than during underwriting.</p>
          <ul class="flag-list">
            <li>Foreign national (limited programs available)</li>
            <li>Expired or invalid ID (must renew before closing)</li>
            <li>No score / locked credit file (manual review needed)</li>
            <li>Interested party contribution ≥ 25% (additional documentation required)</li>
            <li>Gift funds only (helps assets, not income)</li>
            <li>Multiple properties owned (REO schedule required)</li>
          </ul>
        </div>
        <div>
          <div class="docs-box">
            <div class="doc-chips">
              <div class="chip">Government-issued Photo ID</div>
              <div class="chip">Income Documentation</div>
              <div class="chip">2 Months Bank Statements</div>
              <div class="chip">Verification of Assets</div>
              <div class="chip">401(k) / IRA Statements</div>
              <div class="chip">REO Schedule</div>
              <div class="chip">Gift Letter</div>
              <div class="chip">Donor Bank Statement</div>
            </div>
          </div>
          <p style="margin-top:1.2rem; font-size:0.76rem; font-weight:300; color:rgba(247,243,236,0.4); line-height:1.6;">Your document checklist will be tailored to your specific scenario — this is just a representative sample.</p>
        </div>
      </div>
    </div>
  </section>

  <!-- HOW IT WORKS -->
  <section class="steps-section" id="steps">
    <div class="section-inner">
      <div class="section-label">Next Steps</div>
      <h2 class="section-title">Three steps to loan readiness.</h2>
      <div class="gold-rule"></div>
      <div class="steps-track">
        <div class="step">
          <div class="step-num">1</div>
          <div class="step-title">Complete the Tool</div>
          <div class="step-desc">Answer a short set of questions about your financial profile. Takes under five minutes.</div>
        </div>
        <div class="step">
          <div class="step-num">2</div>
          <div class="step-title">Save Your Summary</div>
          <div class="step-desc">Download your Mortgage Readiness Summary and gather the documents on your checklist.</div>
        </div>
        <div class="step">
          <div class="step-num">3</div>
          <div class="step-title">Connect With a Specialist</div>
          <div class="step-desc">Share your summary for a full review. Submit your loan inquiry to get started.</div>
        </div>
      </div>
    </div>
  </section>

  <!-- CTA BAND -->
  <section class="cta-band">
    <h2>Ready to see where you stand?</h2>
    <p>Generate your Mortgage Readiness Summary — then submit it with your loan inquiry.</p>
    <div class="cta-group">
      <a href="https://ngozieomegbu-tool.github.io/HomeLoanProfile/" target="_blank" class="btn-primary">Launch the Tool</a>
      <a href="loan-inquiry-form.html" class="btn-secondary">Submit Loan Inquiry</a>
    </div>
  </section>

  <!-- FOOTER -->
  <footer>
    <div class="footer-brand">NEXA Lending</div>
    <p class="footer-legal">
      This is a pre-underwriting screening tool for informational purposes only and does not constitute a loan commitment, approval, or guarantee of financing. All figures are estimates. Final loan eligibility is subject to full underwriting, lender guidelines, property appraisal, and applicable law. Consult a licensed mortgage professional before making financial decisions.<br/><br/>
      Prepared by Ngozie Omegbu · NMLS ID #2077106 · WI / Nationwide Referrals
    </p>
  </footer>

  <script>
    // Intersection observer for staggered reveals
    const observer = new IntersectionObserver((entries) => {
      entries.forEach(entry => {
        if (entry.isIntersecting) {
          const el = entry.target;
          const siblings = el.parentElement.querySelectorAll('.get-item, .flag-list li, .step');
          const idx = Array.from(siblings).indexOf(el);
          setTimeout(() => el.classList.add('visible'), idx * 90);
          observer.unobserve(el);
        }
      });
    }, { threshold: 0.15 });

    document.querySelectorAll('.get-item, .flag-list li, .step').forEach(el => observer.observe(el));
  </script>
</body>
</html>
