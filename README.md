<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="utf-8">
<meta name="viewport" content="width=device-width, initial-scale=1, viewport-fit=cover">
<title>Sopaan · Force and Translational Dynamics</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link rel="stylesheet" href="https://fonts.googleapis.com/css2?family=Fraunces:opsz,wght@9..144,500;9..144,700&family=Source+Sans+3:wght@400;600;700&family=IBM+Plex+Mono:wght@500;600&display=swap">
<style>
  html,body{margin:0;} img{max-width:100%;} [hidden]{display:none !important;}
  :root{
    --navy:#16264A; --navy-2:#1F3B6B; --gold:#C79A3E; --gold-soft:#F3E7C9;
    --paper:#FBF9F4; --paper-2:#F1EAD8; --card:#FFFFFF;
    --ink:#211E1A; --ink-soft:#655D4C; --rule:#E4DCC8;
    --success:#2E8B57; --success-soft:#E1F2E7;
    --danger:#BF4B45; --danger-soft:#FAE3E1;
    --locked:#C7BEA9;
    --focus:#1F3B6B;
    --accent-text:#1F3B6B; --retry-text:#8A661F;
    color-scheme:light;
  }
  @media (prefers-color-scheme: dark){
    :root:not([data-theme="light"]){
      --navy:#0E1830; --navy-2:#16264A; --gold:#E0B75B; --gold-soft:#3A2F16;
      --paper:#141210; --paper-2:#1C1914; --card:#1C1914;
      --ink:#EDE7DA; --ink-soft:#B2A996; --rule:#3A342A;
      --success:#7BC79A; --success-soft:#1B2E22;
      --danger:#E38884; --danger-soft:#331D1B;
      --locked:#4A4436;
      --focus:#E0B75B;
      --accent-text:#E0B75B; --retry-text:#E0B75B;
      color-scheme:dark;
    }
  }
  :root[data-theme="dark"]{
    --navy:#0E1830; --navy-2:#16264A; --gold:#E0B75B; --gold-soft:#3A2F16;
    --paper:#141210; --paper-2:#1C1914; --card:#1C1914;
    --ink:#EDE7DA; --ink-soft:#B2A996; --rule:#3A342A;
    --success:#7BC79A; --success-soft:#1B2E22;
    --danger:#E38884; --danger-soft:#331D1B;
    --locked:#4A4436;
    --focus:#E0B75B;
    --accent-text:#E0B75B; --retry-text:#E0B75B;
    color-scheme:dark;
  }

  *{box-sizing:border-box;}
  body{background:var(--paper); color:var(--ink); font-family:'Source Sans 3',-apple-system,'Segoe UI',sans-serif; padding-inline:0; padding-block:0;}
  h1,h2,h3{font-family:'Fraunces',Georgia,serif; text-wrap:balance; margin:0;}
  .num{font-family:'IBM Plex Mono',ui-monospace,monospace; font-variant-numeric:tabular-nums;}

  header.brand{
    background:linear-gradient(155deg,var(--navy) 0%, var(--navy-2) 100%);
    color:#F4EFDF; padding-block:calc(20px + env(safe-area-inset-top,0px)) 18px; padding-inline:20px;
  }
  .brand-row{display:flex; align-items:center; gap:12px; max-width:900px; margin:0 auto;}
  .crest{
    width:42px; height:42px; border-radius:10px; background:var(--gold); color:var(--navy);
    display:flex; align-items:center; justify-content:center; font-family:'Fraunces',serif; font-weight:700; font-size:18px; flex-shrink:0;
  }
  .brand-name{font-size:12px; letter-spacing:.08em; text-transform:uppercase; color:var(--gold); font-weight:700;}
  .series-name{font-size:19px; font-weight:700; font-family:'Fraunces',serif;}
  .chapter-eyebrow{max-width:900px; margin:14px auto 0; font-size:12px; letter-spacing:.06em; text-transform:uppercase; color:#AEB9D6;}
  .chapter-title{font-size:28px; max-width:900px; margin:2px auto 0;}
  .chapter-sub{font-size:14.5px; color:var(--gold); font-weight:700; max-width:900px; margin:3px auto 0;}

  .chapter-progress{max-width:900px; margin:14px auto 0; display:flex; align-items:center; gap:10px;}
  .cp-track{flex:1; height:6px; border-radius:99px; background:rgba(255,255,255,.18); overflow:hidden;}
  .cp-fill{height:100%; background:var(--gold); border-radius:99px; transition:width .3s ease;}
  .cp-label{font-size:11.5px; color:#CFD7EA; white-space:nowrap;}

  .tabbar{position:sticky; top:env(safe-area-inset-top,0px); z-index:15; background:var(--paper); border-bottom:1px solid var(--rule); overflow-x:auto; white-space:nowrap;}
  .tabbar-inner{max-width:900px; margin:0 auto; display:flex; padding-inline:16px;}
  .tab-btn{font-family:inherit; font-size:14px; font-weight:600; color:var(--ink-soft); background:none; border:none; padding:13px 16px; cursor:pointer; position:relative; flex-shrink:0;}
  .tab-btn.active{color:var(--accent-text);}
  .tab-btn.active::after{content:''; position:absolute; left:12px; right:12px; bottom:0; height:3px; background:var(--gold); border-radius:3px 3px 0 0;}
  .tab-count{font-size:11px; color:var(--ink-soft); margin-left:5px;}

  .slide-progress{max-width:900px; margin:0 auto; padding:10px 16px 0; display:flex; align-items:center; gap:10px;}
  .sp-track{flex:1; height:5px; border-radius:99px; background:var(--rule); overflow:hidden;}
  .sp-fill{height:100%; background:var(--accent-text); border-radius:99px; transition:width .3s ease;}
  .sp-label{font-size:12px; color:var(--ink-soft); white-space:nowrap; font-weight:600;}

  .wrap{max-width:900px; margin:0 auto; padding:16px 16px calc(110px + env(safe-area-inset-bottom,0px));}

  .qcard{background:var(--card); border:1px solid var(--rule); border-radius:14px; padding:18px;}
  .qhead{display:flex; align-items:flex-start; gap:10px; margin-bottom:10px;}
  .qnum{width:32px; height:32px; border-radius:8px; background:var(--gold-soft); color:var(--accent-text); display:flex; align-items:center; justify-content:center; font-weight:700; font-family:'Fraunces',serif; flex-shrink:0; font-size:14px;}
  .qtext{font-size:16px; line-height:1.55; flex:1;}
  .qtag{font-size:10.5px; color:var(--gold); background:var(--gold-soft); padding:2px 7px; border-radius:99px; font-weight:700; margin-left:6px; white-space:nowrap;}
  .marks-pill{font-size:11px; font-weight:700; color:var(--ink-soft); border:1px solid var(--rule); padding:3px 9px; border-radius:99px; margin-left:auto; flex-shrink:0; white-space:nowrap;}
  .step-badge{font-size:11px; font-weight:700; color:var(--accent-text); background:var(--paper-2); border:1px solid var(--rule); padding:3px 9px; border-radius:99px; display:inline-block; margin-bottom:12px;}

  .options{display:flex; flex-direction:column; gap:8px; margin-top:10px;}
  .opt{display:flex; align-items:center; gap:10px; padding:11px 12px; border:1.5px solid var(--rule); border-radius:10px; cursor:pointer; font-size:15px; background:var(--paper);}
  .opt input{accent-color:var(--navy-2);}
  .opt.is-correct{border-color:var(--success); background:var(--success-soft);}
  .opt.is-wrong{border-color:var(--danger); background:var(--danger-soft);}
  .opt.locked{cursor:not-allowed;}

  .subpart-label{font-weight:700; font-size:12.5px; color:var(--accent-text); text-transform:uppercase; letter-spacing:.03em; margin:14px 0 6px;}
  .or-divider{text-align:center; font-size:11px; font-weight:700; letter-spacing:.08em; color:var(--ink-soft); margin:8px 0;}

  .steps{display:flex; flex-direction:column; gap:10px;}
  .step-line{font-size:14.5px; line-height:1.9; background:var(--paper); border:1px dashed var(--rule); border-radius:10px; padding:9px 12px;}
  .step-line.resolved{opacity:.9;}
  .blank-input{font-family:'IBM Plex Mono',monospace; font-size:14px; border:1.5px solid var(--rule); border-radius:6px; padding:3px 8px; width:120px; background:var(--card); color:var(--ink); margin:0 2px;}
  .blank-input:focus{outline:none; border-color:var(--focus); box-shadow:0 0 0 3px var(--gold-soft);}
  .blank-input.is-correct{border-color:var(--success); background:var(--success-soft);}
  .blank-input.is-wrong{border-color:var(--danger); background:var(--danger-soft);}
  .blank-input[disabled]{opacity:.85;}
  .reveal-note{font-size:12px; color:var(--danger); padding-left:2px; margin-top:-2px;}

  .feedback{font-size:13.5px; padding:10px 12px; border-radius:9px; margin-top:14px; display:none;}
  .feedback.show{display:block;}
  .feedback.ok{background:var(--success-soft); color:var(--success);}
  .feedback.retry{background:var(--gold-soft); color:var(--retry-text);}
  .feedback.reveal{background:var(--danger-soft); color:var(--danger);}
  .feedback.err{background:var(--danger-soft); color:var(--danger);}
  .attempts-dots{display:inline-flex; gap:4px; margin-left:2px;}
  .attempts-dots span{width:6px; height:6px; border-radius:50%; background:var(--ink-soft); opacity:.3; display:inline-block;}
  .attempts-dots span.used{opacity:1; background:var(--danger);}

  .ar-box{background:var(--paper-2); border-radius:10px; padding:10px 12px; margin-bottom:12px; font-size:13px; color:var(--ink-soft);}

  .navbar{
    position:fixed; left:0; right:0; bottom:0; z-index:30; background:var(--paper);
    border-top:1px solid var(--rule); padding:10px 16px calc(10px + env(safe-area-inset-bottom,0px));
  }
  .navbar-inner{max-width:900px; margin:0 auto; display:flex; gap:8px; flex-wrap:wrap; align-items:center;}
  .btn{font-family:inherit; font-size:13.5px; font-weight:700; padding:10px 14px; border-radius:9px; border:1.5px solid var(--rule); background:var(--card); color:var(--ink); cursor:pointer;}
  .btn:hover{border-color:var(--navy-2);}
  .btn:disabled{opacity:.4; cursor:not-allowed;}
  .btn-primary{background:var(--navy-2); color:#fff; border-color:var(--navy-2);}
  .navbar .spacer{flex:1;}

  .fab{position:fixed; right:16px; bottom:calc(74px + env(safe-area-inset-bottom,0px)); background:var(--gold); color:var(--navy); border:none; border-radius:999px; padding:11px 16px; font-family:inherit; font-weight:700; font-size:13px; display:flex; align-items:center; gap:7px; cursor:pointer; box-shadow:0 6px 16px rgba(0,0,0,.18); z-index:35;}
  .fab-badge{background:rgba(255,255,255,.55); border-radius:99px; padding:1px 7px; font-size:11px;}

  .overlay{position:fixed; inset:0; background:rgba(20,18,14,.45); z-index:50; display:none; align-items:flex-end; justify-content:center;}
  .overlay.show{display:flex;}
  .palette{background:var(--card); width:min(480px,100%); max-height:78vh; overflow-y:auto; border-radius:18px 18px 0 0; padding:18px 18px calc(18px + env(safe-area-inset-bottom,0px)); border:1px solid var(--rule); border-bottom:none;}
  @media (min-width:640px){ .overlay{align-items:center;} .palette{border-radius:18px; border-bottom:1px solid var(--rule); max-height:74vh;} }
  .palette-head{display:flex; align-items:center; justify-content:space-between; margin-bottom:6px;}
  .palette-head h2{font-size:16px;}
  .palette-close{background:none; border:none; font-size:20px; color:var(--ink-soft); cursor:pointer; padding:4px;}
  .palette-legend{display:flex; gap:12px; flex-wrap:wrap; font-size:11px; color:var(--ink-soft); margin:10px 0 14px;}
  .palette-legend span{display:inline-flex; align-items:center; gap:5px;}
  .dot{width:9px; height:9px; border-radius:50%; display:inline-block;}
  .dot.correct{background:var(--success);} .dot.revealed{background:var(--danger);}
  .dot.skipped{background:var(--gold);} .dot.locked{background:var(--locked);}
  .dot.current{background:var(--navy-2);}
  .chip-grid{display:grid; grid-template-columns:repeat(auto-fill,minmax(48px,1fr)); gap:8px;}
  .chip{border:1.5px solid var(--rule); border-radius:9px; padding:8px 4px; text-align:center; font-family:'IBM Plex Mono',monospace; font-size:12.5px; font-weight:600; cursor:pointer; background:var(--paper); color:var(--ink);}
  .chip[data-status="correct"]{border-color:var(--success); background:var(--success-soft); color:var(--success);}
  .chip[data-status="revealed"]{border-color:var(--danger); background:var(--danger-soft); color:var(--danger);}
  .chip[data-status="skipped"]{border-color:var(--gold); background:var(--gold-soft); color:var(--retry-text);}
  .chip[data-status="locked"]{border-color:var(--rule); color:var(--locked); cursor:not-allowed; background:var(--paper-2);}
  .chip[data-status="current"]{outline:2px solid var(--navy-2); outline-offset:1px;}

  .toast{position:fixed; left:50%; bottom:calc(140px + env(safe-area-inset-bottom,0px)); transform:translateX(-50%); background:var(--ink); color:var(--paper); padding:9px 16px; border-radius:99px; font-size:13px; opacity:0; pointer-events:none; transition:opacity .25s ease; z-index:60;}
  .toast.show{opacity:1;}

  .done-card{text-align:center; padding:36px 20px;}
  .done-card .big{font-size:38px; margin-bottom:6px;}
  .score-pills{display:flex; gap:10px; justify-content:center; flex-wrap:wrap; margin:16px 0;}
  .score-pill{padding:8px 16px; border-radius:99px; font-size:13px; font-weight:700;}

  footer.brandfoot{max-width:900px; margin:14px auto 0; padding:0 16px calc(110px + env(safe-area-inset-bottom,0px)); text-align:center; font-size:12px; color:var(--ink-soft);}

  .mode-pill{font-family:inherit; font-size:12.5px; font-weight:700; color:var(--navy); background:var(--gold); border:none; border-radius:99px; padding:6px 14px; cursor:pointer; margin-top:12px; display:inline-flex; align-items:center; gap:6px;}
  .mode-pick{display:flex; flex-direction:column; gap:14px; padding:8px 0 24px;}
  .mode-card{background:var(--card); border:1.5px solid var(--rule); border-radius:16px; padding:22px; cursor:pointer; text-align:left;}
  .mode-card:hover{border-color:var(--navy-2);}
  .mode-card .mode-icon{font-size:26px; margin-bottom:8px;}
  .mode-card h3{font-size:18px; margin-bottom:6px;}
  .mode-card p{font-size:13.5px; color:var(--ink-soft); line-height:1.5; margin:0;}
  .quiz-hint{font-size:12.5px; color:var(--ink-soft); background:var(--paper-2); border-radius:9px; padding:8px 12px; margin-bottom:14px;}
  .review-row{border:1px solid var(--rule); border-radius:10px; padding:11px 13px; margin-bottom:10px;}
  .review-tag{font-size:11.5px; font-weight:700; margin-bottom:4px; display:block;}
  .review-tag.ok{color:var(--success);} .review-tag.bad{color:var(--danger);} .review-tag.na{color:var(--ink-soft);}
  .review-q{font-size:13.5px; margin-bottom:6px; color:var(--ink-soft);}
  .review-ans{font-size:13px; margin-bottom:2px;}

  .who-row{max-width:900px; margin:12px auto 0; display:flex; flex-wrap:wrap; gap:8px; align-items:center;}
  .who-row .mode-pill{margin-top:0;}
  .who{display:inline-flex; flex-wrap:wrap; align-items:center; gap:6px; font-size:12.5px; color:#CFD7EA;}
  .who b{color:#F4EFDF;}
  .who button{font-family:inherit; font-size:12px; font-weight:700; color:#F4EFDF; background:rgba(255,255,255,.12); border:1px solid rgba(255,255,255,.22); border-radius:99px; padding:5px 11px; cursor:pointer;}
  .who button:hover{background:rgba(255,255,255,.2);}
  .login-card{max-width:460px; margin:8px auto 0; background:var(--card); border:1px solid var(--rule); border-radius:16px; padding:22px;}
  .login-card h2{font-size:21px; margin-bottom:4px;}
  .login-card p.lead{font-size:13.5px; color:var(--ink-soft); margin:0 0 16px; line-height:1.5;}
  .fld{display:flex; flex-direction:column; gap:5px; margin-bottom:12px;}
  .fld label{font-size:12px; font-weight:700; letter-spacing:.04em; text-transform:uppercase; color:var(--ink-soft);}
  .fld input{font-family:inherit; font-size:15px; padding:10px 12px; border:1.5px solid var(--rule); border-radius:9px; background:var(--paper); color:var(--ink);}
  .fld input:focus{outline:none; border-color:var(--focus); box-shadow:0 0 0 3px var(--gold-soft);}
  .fld-row{display:grid; grid-template-columns:1fr 1fr; gap:10px;}
  .login-err{font-size:13px; color:var(--danger); background:var(--danger-soft); border-radius:8px; padding:8px 10px; margin-bottom:12px;}
  .login-note{font-size:12px; color:var(--ink-soft); margin-top:12px; line-height:1.5;}
  .known{margin:0 0 16px; display:flex; flex-direction:column; gap:6px;}
  .known-label{font-size:12px; font-weight:700; letter-spacing:.04em; text-transform:uppercase; color:var(--ink-soft);}
  .known-btn{display:flex; justify-content:space-between; align-items:center; gap:10px; text-align:left; font-family:inherit; font-size:14.5px; padding:10px 12px; border:1.5px solid var(--rule); border-radius:10px; background:var(--paper); color:var(--ink); cursor:pointer;}
  .known-btn:hover{border-color:var(--navy-2);}
  .known-btn small{font-size:12px; color:var(--ink-soft);}
  .rec-card{background:var(--card); border:1px solid var(--rule); border-radius:14px; padding:18px; margin-bottom:14px;}
  .rec-card h2{font-size:19px; margin-bottom:10px;}
  .rec-card h3{font-size:15px; margin:4px 0 8px;}
  .rec-table-wrap{overflow-x:auto;}
  .rec-table{width:100%; border-collapse:collapse; font-size:13.5px; font-variant-numeric:tabular-nums;}
  .rec-table th{text-align:left; font-size:11.5px; text-transform:uppercase; letter-spacing:.04em; color:var(--ink-soft); padding:6px 8px; border-bottom:1px solid var(--rule); white-space:nowrap;}
  .rec-table td{padding:8px; border-bottom:1px solid var(--rule); white-space:nowrap;}
  .rec-bar{display:inline-block; width:70px; height:6px; border-radius:99px; background:var(--rule); overflow:hidden; vertical-align:middle; margin-right:6px;}
  .rec-bar i{display:block; height:100%; background:var(--success);}
  .rec-empty{font-size:13.5px; color:var(--ink-soft);}
  .sec-sub{max-width:900px; margin:0 auto; padding:10px 16px 0; font-size:12.5px; font-weight:700; color:var(--accent-text); letter-spacing:.02em;}
  .opt{flex-wrap:wrap;}
  .opt-l{font-family:'IBM Plex Mono',monospace; font-size:13px; font-weight:600; color:var(--ink-soft);}
  .opt-t{flex:1; min-width:0;}
  .opt.is-chosen:not(.is-correct):not(.is-wrong){border-color:var(--navy-2); background:var(--gold-soft);}
  .opt-tag{font-size:11px; font-weight:700; padding:2px 8px; border-radius:99px; background:var(--card); border:1px solid currentColor; white-space:nowrap;}
  .opt.is-correct .opt-tag{color:var(--success);} .opt.is-wrong .opt-tag{color:var(--danger);} .opt.is-chosen:not(.is-correct):not(.is-wrong) .opt-tag{color:var(--accent-text);}
  .chosen{font-size:13.5px; margin-top:10px; padding:8px 12px; border-radius:9px;}
  .chosen.ok{background:var(--success-soft); color:var(--success);} .chosen.bad{background:var(--danger-soft); color:var(--danger);}
  .chosen + .chosen{margin-top:6px;}
  .solution{margin-top:14px; border:1px solid var(--rule); border-left:4px solid var(--gold); background:var(--paper-2); border-radius:10px; padding:12px 14px;}
  .sol-h{font-family:'Fraunces',Georgia,serif; font-weight:700; font-size:14px; color:var(--accent-text); margin-bottom:6px;}
  .sol-line{font-size:14.5px; line-height:1.7;}
  .rev-sol summary{cursor:pointer; font-size:12.5px; font-weight:700; color:var(--accent-text); margin-top:6px;}
  .rev-sol .solution{margin-top:8px;}
  .chapter-credit{max-width:900px; margin:4px auto 0; font-size:12px; color:#CFD7EA;}
  footer.brandfoot a{color:inherit;}
  .blank-input.wide{width:260px; max-width:100%; font-family:'Source Sans 3',sans-serif;}
  .blank-input.expr{width:170px; max-width:100%;}
  /*fix-layout*/ .cp-fill,.sp-fill{width:0;} .fld{min-width:0;} .fld input{width:100%; min-width:0; box-sizing:border-box;}
  .fig{margin:6px 0 10px; display:flex; justify-content:center;}
  .figsvg{width:100%; max-width:340px; height:auto; overflow:visible;}
  .figsvg .ln,.figsvg .arm{stroke:var(--ink); stroke-width:1.6; fill:none;}
  .figsvg .arm{stroke:var(--accent-text); stroke-width:2;}
  .figsvg .pt{fill:var(--ink);}
  .figsvg .lb{fill:var(--ink); font:600 13px 'Source Sans 3',sans-serif;}
  .figsvg .al{fill:var(--accent-text); font:700 12px 'Source Sans 3',sans-serif;}
  .figsvg .wg{fill:var(--gold-soft); stroke:var(--gold); stroke-width:1.2;}
  .figsvg .wg2{fill:rgba(199,154,62,.35); stroke:var(--gold); stroke-width:1.2;}
  .figsvg .ra{fill:none; stroke:var(--ink); stroke-width:1.2;}
  .figsvg .ahd{fill:var(--ink);}
  .figsvg .pr{fill:var(--paper-2); stroke:var(--ink-soft); stroke-width:1.2;}
  .figsvg .tk{stroke:var(--ink-soft); stroke-width:.8;}
  .figsvg .po{fill:var(--ink); font:600 8.5px 'IBM Plex Mono',monospace;}
  .figsvg .pi{fill:var(--danger); font:600 7.5px 'IBM Plex Mono',monospace;}
  .figsvg .sh{fill:var(--gold-soft); stroke:var(--ink); stroke-width:1.5; stroke-linejoin:round;}
  .figsvg .sh2{fill:rgba(199,154,62,.38); stroke:var(--ink); stroke-width:1.5; stroke-linejoin:round;}
  .figsvg .sh3{fill:rgba(199,154,62,.22); stroke:var(--ink); stroke-width:1.5; stroke-linejoin:round;}
  .figsvg .none{fill:none;}
  .figsvg .hid{stroke-dasharray:5 4; fill:none;}
  .figsvg .tick{stroke:var(--ink); stroke-width:1.4; fill:none;}
  .figsvg .shd{fill:var(--accent-text); fill-opacity:.55;}
  .figsvg .cell{fill:var(--card); stroke:var(--ink); stroke-width:1.1;}
  .figsvg .dr{fill:var(--danger);} .figsvg .dw{fill:var(--card); stroke:var(--ink); stroke-width:1.2;}
  .figsvg .dotfill{fill:var(--danger);}
  .tt{border-collapse:collapse; font-size:13.5px; margin:4px auto; font-variant-numeric:tabular-nums;} .tt th,.tt td{border:1px solid var(--rule); padding:4px 9px; text-align:left;} .tt th{background:var(--paper-2); font-weight:700;} .ttw{overflow-x:auto; max-width:100%;}
  .fq{display:inline-flex; flex-direction:column; vertical-align:middle; text-align:center; font-size:.82em; line-height:1.12; margin:0 2px;}
  .fq>span:first-child{border-bottom:1.5px solid currentColor; padding:0 2px;}
  .fq>span:last-child{padding:0 2px;}
  .mx{white-space:nowrap;}
  .blank-input.fr{width:110px;}
  @media (prefers-reduced-motion:reduce){ *{transition:none !important;} }
.datline{display:block;margin-top:8px;padding:8px 10px;border-radius:8px;background:var(--paper-2);font:500 14px/1.7 'IBM Plex Mono',monospace;word-spacing:2px;overflow-wrap:anywhere;}

  .theory{display:flex;flex-direction:column;gap:16px;padding-bottom:40px;}
  .hub{display:grid;grid-template-columns:1fr;gap:12px;}
  @media (min-width:640px){ .hub{grid-template-columns:repeat(3,1fr);} }
  .hub-card{background:var(--card);border:1px solid var(--rule);border-radius:14px;padding:16px;display:flex;flex-direction:column;gap:8px;}
  .hub-card h3{font-family:'Fraunces',serif;font-size:18px;margin:0;color:var(--accent-text);}
  .hub-card p{margin:0;font-size:14px;color:var(--ink-soft);line-height:1.5;}
  .hub-btns{display:flex;flex-wrap:wrap;gap:8px;margin-top:auto;}
  .hub-btn{min-height:40px;border:1.5px solid var(--rule);background:var(--paper-2);color:var(--ink);border-radius:10px;padding:8px 12px;font:600 14px 'Source Sans 3',sans-serif;cursor:pointer;text-align:left;}
  .hub-btn:hover{border-color:var(--gold);}
  .hub-btn.primary{background:var(--navy);color:#F4EFDF;border-color:var(--navy);}
  .note{background:var(--card);border:1px solid var(--rule);border-radius:14px;padding:18px;scroll-margin-top:120px;}
  .note h2{font-family:'Fraunces',serif;font-size:22px;margin:0 0 4px;color:var(--ink);}
  .note .lt{font-size:13.5px;color:var(--ink-soft);margin:0 0 12px;}
  .note .lt b{color:var(--accent-text);}
  .note h4{font:700 15px 'Source Sans 3',sans-serif;margin:16px 0 6px;color:var(--accent-text);}
  .note p,.note li{font-size:15.5px;line-height:1.6;}
  .note ul{padding-left:20px;margin:6px 0;}
  .keybox{background:var(--gold-soft);border-left:4px solid var(--gold);border-radius:8px;padding:10px 12px;margin:10px 0;font-size:15px;line-height:1.6;}
  .keybox b{color:var(--ink);}
  .ex{background:var(--paper-2);border-radius:10px;padding:12px;margin:10px 0;}
  .ex .exh{font-family:'Fraunces',serif;font-weight:700;color:var(--accent-text);margin-bottom:4px;}
  .ex .exl{font-size:15px;line-height:1.7;}
  .ttab{width:100%;border-collapse:collapse;font-size:14.5px;margin:8px 0;}
  .ttab th,.ttab td{border:1px solid var(--rule);padding:7px 8px;text-align:left;vertical-align:top;}
  .ttab th{background:var(--paper-2);}
  .tscroll{overflow-x:auto;}
  .mono{font-family:'IBM Plex Mono',monospace;font-size:.92em;}
  @media (max-width:480px){ .ttab{font-size:13.5px;} .ttab th,.ttab td{padding:6px;} }
  .note .figsvg{max-width:100%;height:auto;display:block;margin:8px auto;}


  .rep-top{display:flex;flex-wrap:wrap;gap:18px;align-items:center;justify-content:center;margin-top:8px;}
  .rep-legend{flex:1;min-width:220px;display:flex;flex-direction:column;gap:8px;}
  .rep-cap{font:700 13px 'Source Sans 3',sans-serif;color:var(--ink-soft);text-transform:uppercase;letter-spacing:.05em;}
  .rep-li{display:flex;align-items:center;gap:6px;font-size:15px;}
  .rep-n{margin-left:auto;white-space:nowrap;padding-left:8px;font-family:'IBM Plex Mono',monospace;font-weight:600;}
  .sw{display:inline-block;width:12px;height:12px;border-radius:3px;flex:none;}
  .rep-grid{display:grid;grid-template-columns:1fr;gap:12px;}
  @media (min-width:640px){ .rep-grid{grid-template-columns:1fr 1fr;} }
  .rep-card{background:var(--card);border:1px solid var(--rule);border-radius:14px;padding:14px;display:flex;flex-direction:column;gap:10px;}
  .rep-h{display:flex;align-items:center;gap:8px;font:700 16px 'Source Sans 3',sans-serif;}
  .crit{display:inline-grid;place-items:center;width:28px;height:28px;border-radius:50%;color:var(--card);font:700 15px Fraunces,serif;flex:none;}
  .rep-row{display:flex;gap:14px;align-items:center;}
  .rep-stats{display:flex;flex-direction:column;gap:5px;font-size:14.5px;}
  .rep-stats div{display:flex;align-items:center;gap:6px;}
  .rep-lvl{margin-top:4px;color:var(--accent-text);} .rep-lvl span{color:var(--ink-soft);font-size:13px;}
  .rep-note{font-size:13px;color:var(--ink-soft);}


  .skip-chips{display:flex;flex-wrap:wrap;gap:8px;justify-content:center;margin:12px 0;}
  .skip-chips .chip{min-width:48px;min-height:40px;cursor:pointer;border:1.5px solid var(--gold);background:var(--gold-soft);color:var(--retry-text);border-radius:10px;font:600 14px 'IBM Plex Mono',monospace;}
  .skip-btns{display:flex;flex-wrap:wrap;gap:10px;justify-content:center;margin-top:12px;}


  .kb-toggle{border:none;background:transparent;font-size:15px;cursor:pointer;padding:0 2px;vertical-align:middle;opacity:.7;}
  .vkb{position:fixed;left:0;right:0;bottom:0;z-index:80;background:var(--paper-2);border-top:1px solid var(--rule);box-shadow:0 -6px 20px rgba(0,0,0,.12);padding:6px 6px 8px;display:none;}
  .vkb.show{display:block;}
  .vkb-top{display:flex;justify-content:space-between;align-items:center;max-width:640px;margin:0 auto 4px;font:600 12px 'Source Sans 3',sans-serif;color:var(--ink-soft);}
  .vkb-link{border:none;background:none;color:var(--accent-text);font:600 12px 'Source Sans 3',sans-serif;cursor:pointer;text-decoration:underline;}
  .vkb-row{display:flex;gap:5px;max-width:640px;margin:0 auto 5px;}
  .vkb-k{flex:1;min-height:42px;border:1px solid var(--rule);border-radius:8px;background:var(--card);color:var(--ink);font:600 17px 'IBM Plex Mono',monospace;cursor:pointer;padding:0;}
  .vkb-k.fn{font:600 13px 'Source Sans 3',sans-serif;background:var(--gold-soft);}
  .vkb-k.done{background:var(--navy);color:#F4EFDF;border-color:var(--navy);}
  .vkb-k:active{transform:scale(.96);}
  body.kb-open .wrap{padding-bottom:360px;}
  body.kb-open .fab{display:none;}
  .tool-bar{display:flex;gap:8px;flex-wrap:wrap;margin:-4px 0 10px;}
  .tool-btn{min-height:36px;border:1.5px solid var(--gold);background:var(--gold-soft);color:var(--ink);border-radius:18px;padding:4px 12px;font:600 13.5px 'Source Sans 3',sans-serif;cursor:pointer;}
  .tool-panel{position:fixed;z-index:85;background:var(--card);border:1px solid var(--rule);border-radius:14px;box-shadow:0 10px 30px rgba(0,0,0,.25);display:none;}
  .tool-panel.show{display:block;}
  .tp-head{display:flex;align-items:center;gap:8px;padding:8px 10px;border-bottom:1px solid var(--rule);font:600 14px 'Source Sans 3',sans-serif;}
  .tp-note{font-size:12px;color:var(--ink-soft);font-weight:500;}
  .tp-x{margin-left:auto;border:1px solid var(--rule);background:var(--paper-2);color:var(--ink);border-radius:8px;min-height:32px;padding:2px 10px;cursor:pointer;font:600 13px 'Source Sans 3',sans-serif;}
  .tp-x + .tp-x{margin-left:0;}
  .calc{right:12px;bottom:84px;width:min(330px,calc(100vw - 24px));}
  body.calc-open .wrap{padding-bottom:440px;}
  body.calc-open .fab{display:none;}
  @media (max-width:640px){ .calc{left:6px;right:6px;width:auto;} .calc-keys button{min-height:36px;} }
  .calc-disp{padding:8px 12px;text-align:right;background:var(--paper-2);}
  .calc-expr{font:500 13px 'IBM Plex Mono',monospace;color:var(--ink-soft);min-height:18px;word-break:break-all;}
  .calc-res{font:600 24px 'IBM Plex Mono',monospace;color:var(--ink);word-break:break-all;}
  .calc-keys{display:grid;grid-template-columns:repeat(6,1fr);gap:5px;padding:8px;}
  .calc-keys button{min-height:40px;border:1px solid var(--rule);border-radius:8px;background:var(--card);color:var(--ink);font:600 14px 'IBM Plex Mono',monospace;cursor:pointer;padding:0;}
  .calc-keys button.fn{background:var(--gold-soft);font-family:'Source Sans 3',sans-serif;font-size:13px;}
  .calc-keys button.eq{grid-column:span 2;background:var(--navy);color:#F4EFDF;border-color:var(--navy);}
  .desmos{left:50%;top:50%;transform:translate(-50%,-50%);width:min(760px,calc(100vw - 16px));height:min(560px,calc(100vh - 90px));flex-direction:column;}
  .desmos.show{display:flex;}
  #desmosBox{flex:1;min-height:0;border-radius:0 0 14px 14px;overflow:hidden;}
  .desmos-msg{padding:24px;text-align:center;color:var(--ink-soft);}
  .chip[data-status="skipped"]{cursor:pointer;}
  .chip[data-status="answered"]{border-color:var(--accent-text);color:var(--accent-text);}


  /* larger reading sizes */
  .chapter-eyebrow{font-size:13.5px;}
  .chapter-title{font-size:36px;line-height:1.15;}
  .chapter-sub{font-size:16.5px;}
  .tab-btn{font-size:15.5px;}
  .sec-sub{font-size:15px;}
  .qtext{font-size:19px;line-height:1.55;}
  .qnum{width:36px;height:36px;font-size:16px;}
  .opt{font-size:17.5px;padding:12px 14px;}
  .step-line{font-size:17.5px;line-height:2;}
  .blank-input{font-size:16px;}
  .sol-line{font-size:16.5px;}
  .feedback{font-size:15px;}
  .note h2{font-size:28px;}
  .note h4{font-size:19px;}
  .note p,.note li{font-size:17.5px;line-height:1.65;}
  .note .lt{font-size:15.5px;}
  .ex .exh{font-size:18px;} .ex .exl{font-size:16.5px;}
  .keybox{font-size:16.5px;}
  .ttab{font-size:15.5px;}
  .hub-card h3{font-size:21px;} .hub-card p{font-size:15.5px;} .hub-btn{font-size:15px;}
  @media (max-width:480px){ .chapter-title{font-size:30px;} .qtext{font-size:18px;} .opt,.step-line{font-size:16.5px;} .note h2{font-size:24px;} .note p,.note li{font-size:16.5px;} }
</style>
</head>
<body>
<header class="brand">
  <div class="brand-row">
    <div class="crest">BM</div>
    <div>
      <div class="brand-name">Brain &amp; Mind Academy</div>
      <div class="series-name">Sopaan <span style="font-weight:400;font-size:14px;color:#CFD7EA;">Practice Series</span></div>
    </div>
  </div>
  <div class="chapter-eyebrow">AP Physics 1 · Chapter 2</div>
  <div class="chapter-title">Force and Translational Dynamics</div>
  <div class="chapter-sub">Theory Notes · Practice by Learning Objective · Tests A–D</div><div class="chapter-credit">Organised by AP Physics 1 CED learning objectives · Unit 2</div>
  <div class="chapter-progress">
    <div class="cp-track"><div class="cp-fill" id="cpFill"></div></div>
    <div class="cp-label" id="cpLabel">0% complete</div>
  </div>
  <div class="who-row"><button class="mode-pill" id="modePill" hidden>Choose a mode</button><span class="who" id="whoBar" hidden></span></div>
</header>

<nav class="tabbar"><div class="tabbar-inner" id="tabbar"></div></nav>
<div class="sec-sub" id="secSub"></div><div class="slide-progress"><div class="sp-track"><div class="sp-fill" id="spFill"></div></div><div class="sp-label" id="spLabel">Question 1 of 49</div></div>
<div class="wrap" id="wrap"></div>
<footer class="brandfoot">Brain &amp; Mind Academy · Sopaan Practice Series · AP Physics 1 · Chapter 2<br>Organised by the topics and learning objectives of the AP Physics 1 Course and Exam Description (College Board, 2024), Unit 2. Theory notes, questions, tests and worked solutions are written by Brain &amp; Mind Academy; no workbook or College Board questions are reproduced.</footer>

<div class="navbar"><div class="navbar-inner" id="navbarInner"></div></div>
<button class="fab" id="paletteFab"><span>Questions</span><span class="fab-badge" id="fabBadge">0/49</span></button>

<div class="overlay" id="overlay">
  <div class="palette" role="dialog" aria-label="Question palette">
    <div class="palette-head"><h2 id="paletteTitle">Question palette</h2><button class="palette-close" id="paletteClose">&times;</button></div>
    <div class="palette-legend">
      <span><i class="dot current"></i>Current</span><span><i class="dot correct"></i>Correct</span>
      <span><i class="dot revealed"></i>Revealed</span><span><i class="dot skipped"></i>Skipped</span>
      <span><i class="dot locked"></i>Locked</span>
    </div>
    <div class="chip-grid" id="paletteBody"></div>
  </div>
</div>
<div class="toast" id="toast"></div>

<script>
(function(){
"use strict";

/* ================= audio ================= */
var audioCtx=null;
function ensureAudio(){ if(!audioCtx){ try{ audioCtx=new (window.AudioContext||window.webkitAudioContext)(); }catch(e){} } return audioCtx; }
function playTone(freqs,dur,type){
  var ctx=ensureAudio(); if(!ctx) return;
  try{
    var t0=ctx.currentTime;
    freqs.forEach(function(f,i){
      var o=ctx.createOscillator(), g=ctx.createGain();
      o.type=type||'sine'; o.frequency.value=f;
      var start=t0+i*dur;
      g.gain.setValueAtTime(0.0001,start);
      g.gain.exponentialRampToValueAtTime(0.16,start+0.02);
      g.gain.exponentialRampToValueAtTime(0.0001,start+dur);
      o.connect(g); g.connect(ctx.destination);
      o.start(start); o.stop(start+dur+0.02);
    });
  }catch(e){}
}
function playSuccess(){ playTone([523.25,659.25,783.99],0.11,'sine'); }
function playWrong(){ playTone([220,185],0.14,'square'); }
function playReveal(){ playTone([300,220],0.16,'triangle'); }

/* ================= helpers ================= */
function norm(s){
  return String(s===undefined||s===null?'':s).trim().toLowerCase().replace(/\s+/g,'')
    .replace(/[×∗*·]/g,'x').replace(/÷/g,'/').replace(/–|—|−/g,'-')
    .replace(/[²]/g,'^2').replace(/[³]/g,'^3').replace(/[⁴]/g,'^4').replace(/[⁵]/g,'^5')
    .replace(/[⁶]/g,'^6').replace(/[⁷]/g,'^7').replace(/[⁸]/g,'^8').replace(/[⁹]/g,'^9')
    .replace(/\^/g,'');
}
function parseNum(s){
  if(s===undefined||s===null) return null;
  var t=String(s).trim().replace(/,/g,'').replace(/[−–—]/g,'-').replace(/\s+/g,''); if(t==='') return null;
  var neg=false; if(t[0]==='-'){neg=true;t=t.slice(1);}
  var m=t.match(/^(\d+)\/(\d+)$/);
  if(m){ var v=parseInt(m[1],10)/parseInt(m[2],10); return neg?-v:v; }
  if(/^\d+(\.\d+)?$/.test(t)){ var v2=parseFloat(t); return neg?-v2:v2; }
  return null;
}
/* ---- expression checker: compares answers like (P-2w)/2 and P/2-w at random values ---- */
function exprPrep(s){
  return String(s).toLowerCase().replace(/\s+/g,'').replace(/^[a-z]\(x\)=/i,'').replace(/^y=/i,'').replace(/[×∗·]/g,'*').replace(/÷/g,'/').replace(/[−–—]/g,'-')
    .replace(/²/g,'^2').replace(/³/g,'^3').replace(/⁴/g,'^4').replace(/⁵/g,'^5').replace(/⁶/g,'^6').replace(/⁷/g,'^7').replace(/⁸/g,'^8').replace(/⁹/g,'^9').replace(/π/g,'#').replace(/pi/gi,'#').replace(/½/g,'(1/2)');
}
function exprCompile(src){
  var s=exprPrep(src), i=0, toks=[], absDepth=0;
  while(i<s.length){
    var ch=s[i];
    if(/[0-9.]/.test(ch)){ var j=i; while(j<s.length && /[0-9.]/.test(s[j])) j++; toks.push({k:'n',v:parseFloat(s.slice(i,j))}); i=j; continue; }
    if(/[a-zA-Z#]/.test(ch)){ toks.push({k:'v',v:ch}); i++; continue; }
    if(ch==='|'){ var pv=toks[toks.length-1]; var opn=(absDepth===0)||!pv||('+-*/^(['.indexOf(pv.k)>=0); if(opn){ absDepth++; toks.push({k:'['}); } else { absDepth--; toks.push({k:']'}); } i++; continue; }
    if('+-*/^()'.indexOf(ch)>=0){ toks.push({k:ch}); i++; continue; }
    return null;
  }
  var out=[];
  for(var t=0;t<toks.length;t++){
    var a=toks[t], b=out[out.length-1];
    if(b && (b.k==='n'||b.k==='v'||b.k===')'||b.k===']') && (a.k==='n'||a.k==='v'||a.k==='('||a.k==='[')) out.push({k:'&'});
    out.push(a);
  }
  var p=0;
  function peek(){ return out[p]; }
  function parseE(){ var n=parseT(); while(peek() && (peek().k==='+'||peek().k==='-')){ var o=out[p++].k, r=parseT(); n=(function(l,r,o){return function(e){ return o==='+'?l(e)+r(e):l(e)-r(e); };})(n,r,o); } return n; }
  function parseI(){ var n=parseU(); while(peek() && peek().k==='&'){ p++; var r=parseP(); n=(function(l,r){return function(e){ return l(e)*r(e); };})(n,r); } return n; }
  function parseT(){ var n=parseI(); while(peek() && (peek().k==='*'||peek().k==='/')){ var o=out[p++].k, r=parseI(); n=(function(l,r,o){return function(e){ return o==='*'?l(e)*r(e):l(e)/r(e); };})(n,r,o); } return n; }
  function parseU(){ if(peek() && peek().k==='-'){ p++; var u=parseU(); return function(e){ return -u(e); }; } if(peek() && peek().k==='+'){ p++; return parseU(); } return parseP(); }
  function parseP(){ var b=parseA(); if(peek() && peek().k==='^'){ p++; var x=parseU(); return function(e){ return Math.pow(b(e),x(e)); }; } return b; }
  function parseA(){
    var t=out[p++]; if(!t) throw 0;
    if(t.k==='n') return function(){ return t.v; };
    if(t.k==='v') return t.v==='#' ? function(){ return Math.PI; } : function(e){ return e[t.v]; };
    if(t.k==='('){ var n=parseE(); if(!peek()||peek().k!==')') throw 0; p++; return n; }
    if(t.k==='['){ var m=parseE(); if(!peek()||peek().k!==']') throw 0; p++; return function(e){ return Math.abs(m(e)); }; }
    throw 0;
  }
  try{ var f=parseE(); if(p!==out.length) return null; return f; }catch(e){ return null; }
}
function exprEqual(input,answer){
  var f=exprCompile(input), g=exprCompile(answer); if(!f||!g) return false;
  var hits=0;
  for(var trial=0;trial<8;trial++){
    var env={}; 'abcdefghijklmnopqrstuvwxyzABCDEFGHIJKLMNOPQRSTUVWXYZ'.split('').forEach(function(c){ env[c]=1.3+Math.random()*4.1; });
    var x=f(env), y=g(env);
    if(!isFinite(x)||!isFinite(y)) continue;
    if(Math.abs(x-y)>1e-7*Math.max(1,Math.abs(x),Math.abs(y))) return false;
    hits++;
  }
  return hits>=3;
}
function wordsNorm(s){ return String(s||'').toLowerCase().replace(/\band\b/g,' ').replace(/[^a-z]/g,''); }
function listNorm(s){ return (String(s||'').replace(/[−–—]/g,'-').replace(/(\d) (?=\d{3}\b)/g,'$1').match(/-?\d+(\.\d+)?/g)||[]).join(','); }
function powNorm(s){ return String(s||'').toLowerCase().replace(/\s+/g,'').replace(/[×∗*·.]/g,'x').replace(/[⁰¹²³⁴⁵⁶⁷⁸⁹]+/g,function(m){ return '^'+m.split('').map(function(c){ return '⁰¹²³⁴⁵⁶⁷⁸⁹'.indexOf(c); }).join(''); }).replace(/\^1(?!\d)/g,''); }
function fr(s){ return String(s).replace(/\{(\d+) (\d+)\/(\d+)\}/g,'<span class="mx">$1<span class="fq"><span>$2</span><span>$3</span></span></span>').replace(/\{(\d+)\/(\d+)\}/g,'<span class="fq"><span>$1</span><span>$2</span></span>'); }
function gcdI(a,b){ a=Math.abs(a); b=Math.abs(b); while(b){ var t=a%b; a=b; b=t; } return a; }
function fracParse(s){ s=String(s===undefined||s===null?'':s).trim().replace(/[\u2044\u2215\u00f7]/g,'/').replace(/\s+/g,' ').replace(/\s*\/\s*/g,'/'); var m;
  if((m=s.match(/^(-?\d+)$/))) return {v:+m[1],form:'int',n:+m[1],d:1};
  if((m=s.match(/^(-?\d+)\/(\d+)$/))){ if(+m[2]===0) return null; return {v:m[1]/m[2],form:'frac',n:+m[1],d:+m[2]}; }
  if((m=s.match(/^(\d+)(?: |\+|-)(\d+)\/(\d+)$/))){ if(+m[3]===0) return null; return {v:+m[1]+m[2]/m[3],form:'mixed',w:+m[1],n:+m[2],d:+m[3]}; }
  if((m=s.match(/^-?\d*\.\d+$/))) return {v:parseFloat(s),form:'dec'};
  return null; }
function fracOK(mode,input,answer){
  if(mode==='flist'){ var A=String(input).split(/[,;]/).map(function(x){return x.trim();}).filter(Boolean), K=String(answer).split(/[,;]/).map(function(x){return x.trim();});
    if(A.length!==K.length) return false; return A.every(function(x,i){ var a=fracParse(x), k=fracParse(K[i]); return a&&k&&Math.abs(a.v-k.v)<1e-9; }); }
  var a=fracParse(input), k=fracParse(answer); if(!a||!k) return false;
  var same=Math.abs(a.v-k.v)<1e-9; if(!same) return false;
  if(mode==='fv') return true;
  if(mode==='dec') return a.form==='dec'||a.form==='int';
  if(mode==='fe') return (a.form==='frac'&&k.form==='frac'&&a.n===k.n&&a.d===k.d)||(a.form==='int'&&k.form==='int');
  if(mode==='fi') return a.form==='frac'||(a.form==='int'&&k.form==='int');
  if(mode==='fl') return a.form==='int'||(a.form==='frac'&&gcdI(a.n,a.d)===1)||(a.form==='mixed'&&a.n<a.d&&gcdI(a.n,a.d)===1);
  if(mode==='fm') return a.form==='int'||(a.form==='mixed'&&a.n>0&&a.n<a.d&&gcdI(a.n,a.d)===1);
  return false; }
function answerMatches(input,answer,accept,expr){
  if(expr==='dec'||expr==='fv'||expr==='fe'||expr==='fl'||expr==='fm'||expr==='fi'||expr==='flist'){ if(input===undefined||input===null||String(input).trim()==='') return false; return fracOK(expr,input,answer); }
  if(input===undefined||input===null||String(input).trim()==='') return false;
  if(expr==='words'){ return [answer].concat(accept||[]).some(function(a){ if(/\d/.test(a)) return norm(a)===norm(input); var w=wordsNorm(a); return w!=='' && w===wordsNorm(input); }); }
  if(expr==='list'){ return [answer].concat(accept||[]).some(function(a){ return listNorm(a)===listNorm(input); }); }
  if(expr==='pow'){ return [answer].concat(accept||[]).some(function(a){ return powNorm(a)===powNorm(input); }); }
  if(expr==='time'){ var tn=function(x){ var t=String(x).toLowerCase().replace(/[\s.]/g,'').replace(/[:h]/g,''); if(/^\d{3}(am|pm)?$/.test(t)) t='0'+t; return t; }; return [answer].concat(accept||[]).some(function(a){ return tn(a)===tn(input); }); }
  if(expr==='glist'){ var gn=function(x){ return String(x).toUpperCase().split(/[\s,;]+/).filter(Boolean).sort().join(','); }; return [answer].concat(accept||[]).some(function(a){ return gn(a)===gn(input); }); }
  if(expr==='coord'){ var cn=function(x){ return String(x).replace(/[\u2212\u2013\u2014]/g,'-').replace(/[\s()\[\]]/g,''); }; return [answer].concat(accept||[]).some(function(a){ return cn(a)===cn(input); }); }
  if(expr==='dlist'){ var dn=function(x){ return (String(x).replace(/[−–—]/g,'-').match(/-?\d*\.?\d+/g)||[]).map(Number).join(','); }; return [answer].concat(accept||[]).some(function(a){ return dn(a)===dn(input); }); }
  if(expr==='set'){ var sn=function(x){ return (String(x).match(/-?\d+/g)||[]).map(Number).sort(function(a,b){return a-b;}).join(','); }; return [answer].concat(accept||[]).some(function(a){ return sn(a)===sn(input); }); }
  if(expr==='primes'){ var pn=function(x){ var t=powNorm(x).replace(/[^0-9x^]/g,''); var out=[]; t.split('x').forEach(function(tok){ if(!tok) return; var m=tok.split('^'); var b=+m[0], e=m[1]?+m[1]:1; for(var i=0;i<e;i++) out.push(b); }); return out.sort(function(a,b){return a-b;}).join(','); }; return [answer].concat(accept||[]).some(function(a){ return pn(a)===pn(input); }); }
  if(expr==='angle'){ var an=function(x){ return String(x).toUpperCase().replace(/[^A-Z]/g,''); }; var k=an(answer), v=an(input); return v===k || v===k.split('').reverse().join(''); }
  if(expr==='trans'){ var tv=function(x){ var s=String(x).toLowerCase().replace(/[−–—]/g,'-').replace(/\b(units?|squares?|and|then|steps?|to|the|a)\b/g,' ').replace(/[,;.]/g,' '); var re=/(\d+)\s*(right|left|up|down|r|l|u|d)\b/g, m, dx=0, dy=0, n=0; while((m=re.exec(s))){ var v=+m[1], d=m[2][0]; if(d==='r')dx+=v; else if(d==='l')dx-=v; else if(d==='u')dy+=v; else dy-=v; n++; } if(!n||s.replace(re,'').replace(/\s+/g,'')!=='') return null; return dx+','+dy; }; var ti=tv(input); return ti!==null && [answer].concat(accept||[]).some(function(a){ return tv(a)===ti; }); }
  if(expr==='rot'){ var rv=function(x){ var s=String(x).toLowerCase().replace(/quarter[\s-]*turn/g,'90').replace(/half[\s-]*turn/g,'180').replace(/three[\s-]*quarter[\s-]*turn/g,'270'); var m=s.match(/\b(90|180|270)\b/); if(!m) return null; var a=+m[1]; if(a===180) return '180'; var dir=/anti|counter|acw|ccw/.test(s)?-1:(/clockwise|\bcw\b/.test(s)?1:0); if(!dir) return null; return String(((a*dir)%360+360)%360); }; var ri=rv(input); return ri!==null && ri===rv(answer); }
  if(expr==='expanded'){ var f=function(x){ return String(x).replace(/\s+/g,'').replace(/,/g,''); }; return [answer].concat(accept||[]).some(function(a){ return f(a)===f(input); }); }
  if(expr===true && input!==undefined && input!==null && String(input).trim()!==''){
    if(exprEqual(input,answer)) return true;
    var alt=String(input).replace(/\/\s*(\d+(?:\.\d+)?)\s*([a-zA-Z(])/g,'/$1*$2'); if(alt!==String(input) && exprEqual(alt,answer)) return true;
    return (accept||[]).some(function(a){ return exprEqual(input,a); });
  }
  if(input===undefined||input===null||String(input).trim()==='') return false;
  var n1=parseNum(input), n2=parseNum(answer);
  if(n1!==null && n2!==null){ if(Math.abs(n1-n2)<1e-3) return true; return (accept||[]).some(function(a){ var n3=parseNum(a); return n3!==null && Math.abs(n1-n3)<1e-3; }); }
  var cands=[answer].concat(accept||[]); var ni=norm(input);
  for(var i=0;i<cands.length;i++){ if(norm(cands[i])===ni) return true; }
  return false;
}
function esc(s){ return String(s).replace(/&/g,'&amp;').replace(/</g,'&lt;'); }

/* ================= DATA ================= */
var AR_OPTIONS = ["Both A and R are true, and R is the correct explanation of A","Both A and R are true, but R is NOT the correct explanation of A","A is true but R is false","A is false but R is true"];
var THEORY = "<div class=\"hub\"><div class=\"hub-card\"><h3>📖 Theory notes</h3><p>Notes for each CED topic, with the learning objectives, equations, free-body diagrams, graphs and worked examples.</p><div class=\"hub-btns\"><button class=\"hub-btn\" data-jump=\"n21\">Topic 2.1</button><button class=\"hub-btn\" data-jump=\"n22\">Topic 2.2</button><button class=\"hub-btn\" data-jump=\"n23\">Topic 2.3</button><button class=\"hub-btn\" data-jump=\"n24\">Topic 2.4</button><button class=\"hub-btn\" data-jump=\"n25\">Topic 2.5</button><button class=\"hub-btn\" data-jump=\"n26\">Topic 2.6</button><button class=\"hub-btn\" data-jump=\"n27\">Topic 2.7</button><button class=\"hub-btn\" data-jump=\"n28\">Topic 2.8</button><button class=\"hub-btn\" data-jump=\"n29\">Topic 2.9</button></div></div><div class=\"hub-card\"><h3>🎯 Practice by learning objective</h3><p>One practice sheet per learning objective: multiple choice first, then step-by-step blanks. 🧮 and 📈 appear where a calculator or graph helps.</p><div class=\"hub-btns\"><div class=\"hub-grp\">Topic 2.1 · Systems and Center of Mass</div><button class=\"hub-btn\" data-go=\"s1\">2.1.A · Systems</button><button class=\"hub-btn\" data-go=\"s2\">2.1.B · Center of mass</button><div class=\"hub-grp\">Topic 2.2 · Forces and Free-Body Diagrams</div><button class=\"hub-btn\" data-go=\"s3\">2.2.A · Forces as interactions</button><button class=\"hub-btn\" data-go=\"s4\">2.2.B · Free-body diagrams</button><div class=\"hub-grp\">Topic 2.3 · Newton's Third Law</div><button class=\"hub-btn\" data-go=\"s5\">2.3.A · Newton's third law</button><div class=\"hub-grp\">Topic 2.4 · Newton's First Law</div><button class=\"hub-btn\" data-go=\"s6\">2.4.A · Newton's first law</button><div class=\"hub-grp\">Topic 2.5 · Newton's Second Law</div><button class=\"hub-btn\" data-go=\"s7\">2.5.A (i) · Newton's second law</button><button class=\"hub-btn\" data-go=\"s8\">2.5.A (ii) · Connected objects and ramps</button><div class=\"hub-grp\">Topic 2.6 · Gravitational Force</div><button class=\"hub-btn\" data-go=\"s9\">2.6.A · Universal gravitation</button><button class=\"hub-btn\" data-go=\"s10\">2.6.B · Apparent weight</button><button class=\"hub-btn\" data-go=\"s11\">2.6.C · Inertial and gravitational mass</button><div class=\"hub-grp\">Topic 2.7 · Kinetic and Static Friction</div><button class=\"hub-btn\" data-go=\"s12\">2.7.A · Kinetic friction</button><button class=\"hub-btn\" data-go=\"s13\">2.7.B · Static friction</button><div class=\"hub-grp\">Topic 2.8 · Spring Forces</div><button class=\"hub-btn\" data-go=\"s14\">2.8.A · Spring forces</button><div class=\"hub-grp\">Topic 2.9 · Circular Motion</div><button class=\"hub-btn\" data-go=\"s15\">2.9.A · Circular motion</button><button class=\"hub-btn\" data-go=\"s16\">2.9.B · Circular orbits</button></div></div><div class=\"hub-card\"><h3>📝 Unit test</h3><p>Four tests, one per category. Take them in Quiz mode, then open the report for your pie charts.</p><div class=\"hub-btns\"><button class=\"hub-btn\" data-go=\"s17\">Test A · Knowing and understanding</button><button class=\"hub-btn\" data-go=\"s18\">Test B · Investigating patterns</button><button class=\"hub-btn\" data-go=\"s19\">Test C · Communicating</button><button class=\"hub-btn\" data-go=\"s20\">Test D · Applying physics in real-life contexts</button><button class=\"hub-btn primary\" data-go=\"report\">📊 View my report</button></div></div></div><style>.hub-grp{width:100%;font:700 12px 'Source Sans 3',sans-serif;color:var(--ink-soft);text-transform:uppercase;letter-spacing:.05em;margin-top:6px;}</style><section class=\"note\" id=\"nintro\"><h2>About this unit</h2><p>Unit 2 of AP Physics 1 is <b>dynamics</b>: <i>why</i> things move the way they do. Forces are interactions between objects; Newton's three laws connect the forces on a system to its acceleration. The unit then studies the forces you meet most often — gravity, friction and springs — and ends with circular motion and orbits. There is one practice tab for each learning objective (2.5.A is large, so it has two tabs).</p><div class=\"tscroll\"><table class=\"ttab\"><tr><th>Topic</th><th>Learning objective</th><th>Practice tab</th></tr><tr><td>2.1</td><td><b>2.1.A</b> Describe the properties and interactions of a system.</td><td>2.1.A</td></tr><tr><td>2.1</td><td><b>2.1.B</b> Describe the location of a system's center of mass with respect to the system's constituent parts.</td><td>2.1.B</td></tr><tr><td>2.2</td><td><b>2.2.A</b> Describe a force as an interaction between two objects or systems.</td><td>2.2.A</td></tr><tr><td>2.2</td><td><b>2.2.B</b> Describe the forces exerted on an object or system using a free-body diagram.</td><td>2.2.B</td></tr><tr><td>2.3</td><td><b>2.3.A</b> Describe the interaction of two objects using Newton's third law and a representation of paired forces exerted on each object.</td><td>2.3.A</td></tr><tr><td>2.4</td><td><b>2.4.A</b> Describe the conditions under which a system's velocity remains constant.</td><td>2.4.A</td></tr><tr><td>2.5</td><td><b>2.5.A</b> Describe the conditions under which a system's velocity changes (single objects).</td><td>2.5.A (i)</td></tr><tr><td>2.5</td><td><b>2.5.A</b> Describe the conditions under which a system's velocity changes (connected objects, pulleys and inclines).</td><td>2.5.A (ii)</td></tr><tr><td>2.6</td><td><b>2.6.A</b> Describe the gravitational interaction between two objects or systems with mass.</td><td>2.6.A</td></tr><tr><td>2.6</td><td><b>2.6.B</b> Describe the conditions under which the magnitude of a system's apparent weight is different from the magnitude of the gravitational force exerted on that system.</td><td>2.6.B</td></tr><tr><td>2.6</td><td><b>2.6.C</b> Describe inertial and gravitational mass.</td><td>2.6.C</td></tr><tr><td>2.7</td><td><b>2.7.A</b> Describe kinetic friction between two surfaces.</td><td>2.7.A</td></tr><tr><td>2.7</td><td><b>2.7.B</b> Describe static friction between two surfaces.</td><td>2.7.B</td></tr><tr><td>2.8</td><td><b>2.8.A</b> Describe the force exerted on an object by an ideal spring.</td><td>2.8.A</td></tr><tr><td>2.9</td><td><b>2.9.A</b> Describe the motion of an object traveling in a circular path.</td><td>2.9.A</td></tr><tr><td>2.9</td><td><b>2.9.B</b> Describe circular orbits using Kepler's third law.</td><td>2.9.B</td></tr></table></div><div class=\"tscroll\"><table class=\"ttab\"><tr><th>Relationship</th><th>Meaning</th></tr><tr><td class=\"mono\">x<sub>cm</sub>&nbsp;=&nbsp;Σm<sub>i</sub>x<sub>i</sub> ÷ Σm<sub>i</sub></td><td>centre of mass</td></tr><tr><td class=\"mono\">a<sub>sys</sub>&nbsp;=&nbsp;ΣF ÷ m<sub>sys</sub></td><td>Newton's second law (ΣF = 0 ⇔ constant velocity)</td></tr><tr><td class=\"mono\">F<sub>AB</sub>&nbsp;=&nbsp;−F<sub>BA</sub></td><td>Newton's third law</td></tr><tr><td class=\"mono\">F<sub>g</sub>&nbsp;=&nbsp;Gm<sub>1</sub>m<sub>2</sub> ÷ r²</td><td>universal gravitation, G = 6.67 × 10⁻¹¹ N·m²/kg²</td></tr><tr><td class=\"mono\">g&nbsp;=&nbsp;GM ÷ r², F<sub>g</sub>&nbsp;=&nbsp;mg</td><td>gravitational field</td></tr><tr><td class=\"mono\">F<sub>f,k</sub>&nbsp;=&nbsp;μ<sub>k</sub>F<sub>N</sub></td><td>kinetic friction</td></tr><tr><td class=\"mono\">F<sub>f,s</sub> ≤ μ<sub>s</sub>F<sub>N</sub></td><td>static friction</td></tr><tr><td class=\"mono\">F<sub>s</sub>&nbsp;=&nbsp;−kΔx</td><td>ideal spring (Hooke's law)</td></tr><tr><td class=\"mono\">a<sub>c</sub>&nbsp;=&nbsp;v² ÷ r, v&nbsp;=&nbsp;2πr ÷ T</td><td>uniform circular motion</td></tr><tr><td class=\"mono\">T²&nbsp;=&nbsp;(4π² ÷ GM)R³</td><td>Kepler's third law (circular orbit)</td></tr></table></div><p>Use <b>g ≈ 10 m/s²</b> (and a gravitational field of 10 N/kg) near Earth's surface, and ignore air resistance unless told otherwise. Rounded answers are accepted within about 1%.</p><div class=\"tscroll\"><table class=\"ttab\"><tr><th>Test</th><th>Category</th><th>What it checks</th></tr><tr><td>A</td><td>Knowing and understanding</td><td>Laws, force models and equations used correctly.</td></tr><tr><td>B</td><td>Investigating patterns</td><td>Finding relationships (F–a, friction–normal force, spring, orbit data) and predicting.</td></tr><tr><td>C</td><td>Communicating</td><td>Free-body diagrams, units, signs, significant figures, spotting errors.</td></tr><tr><td>D</td><td>Applying physics in real-life contexts</td><td>Vehicles, lifts, sport and satellites; judging reasonableness.</td></tr></table></div><p><b>Tools:</b> every blank opens an on-screen keyboard (⌨️ brings it back). 🧮 opens a scientific calculator (degrees; Insert puts the result in the blank). 📈 opens a Desmos graph set up for the question.</p></section><section class=\"note\" id=\"n21\"><h2>Topic 2.1 · Systems and Center of Mass</h2><p class=\"lt\"><b>Learning objectives</b></p><ul class=\"lt\"><li><b>2.1.A</b> Describe the properties and interactions of a system.</li><li><b>2.1.B</b> Describe the location of a system's center of mass with respect to the system's constituent parts.</li></ul><p>A <b>system</b> is the object or collection of objects we choose to study; everything else is the <b>surroundings</b>. A system has properties (mass, charge, …) determined by the objects inside it. When its internal structure does not matter for the question, a system can be modelled as a <b>single object</b> (a point).</p><p>Forces between objects <i>inside</i> the system are <b>internal</b>; forces exerted by objects <i>outside</i> are <b>external</b>. Only external forces can change the velocity of the system's centre of mass. Choosing a different system changes which forces count as external.</p><h4>Centre of mass</h4><p>The centre of mass is the mass-weighted average position:</p><div class=\"tscroll\"><table class=\"ttab\"><tr><th>Direction</th><th>Centre of mass</th></tr><tr><td>x</td><td class=\"mono\">x<sub>cm</sub>&nbsp;=&nbsp;(m<sub>1</sub>x<sub>1</sub> + m<sub>2</sub>x<sub>2</sub> + …) ÷ (m<sub>1</sub> + m<sub>2</sub> + …)</td></tr><tr><td>y</td><td class=\"mono\">y<sub>cm</sub>&nbsp;=&nbsp;Σm<sub>i</sub>y<sub>i</sub> ÷ Σm<sub>i</sub></td></tr></table></div><p>For a uniform, symmetric object the centre of mass is at the geometric centre. It is always closer to the more massive parts and can lie outside the material (a ring, a boomerang, an L-shaped bracket).</p><div class=\"fig\"><svg class=\"figsvg\" viewBox=\"0 0 300 90\" role=\"img\"><defs><marker id=\"ah\" viewBox=\"0 0 10 10\" refX=\"9\" refY=\"5\" markerWidth=\"7\" markerHeight=\"7\" orient=\"auto\"><path d=\"M0,1 L10,5 L0,9 z\" class=\"ahd\"/></marker><marker id=\"ahs\" viewBox=\"0 0 10 10\" refX=\"1\" refY=\"5\" markerWidth=\"7\" markerHeight=\"7\" orient=\"auto\"><path d=\"M10,1 L0,5 L10,9 z\" class=\"ahd\"/></marker></defs><line x1=\"24\" y1=\"44\" x2=\"276\" y2=\"44\" style=\"stroke:var(--ink);stroke-width:3\"/><circle cx=\"24.0\" cy=\"44\" r=\"11\" style=\"fill:var(--gold-soft);stroke:var(--ink);stroke-width:1.3\"/><text class=\"lb\" x=\"24.0\" y=\"22.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">2 kg</text><text class=\"po\" x=\"24.0\" y=\"68.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">0 m</text><circle cx=\"276.0\" cy=\"44\" r=\"11\" style=\"fill:var(--gold-soft);stroke:var(--ink);stroke-width:1.3\"/><text class=\"lb\" x=\"276.0\" y=\"22.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">4 kg</text><text class=\"po\" x=\"276.0\" y=\"68.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">1.2 m</text></svg></div><div class=\"ex\"><div class=\"exh\">Worked example 1 · Two masses on a light rod</div><div class=\"exl\">2 kg at x = 0 and 4 kg at x = 1.2 m.<br>x<sub>cm</sub> = (2 × 0 + 4 × 1.2) ÷ 6 = <b>0.80 m</b> — twice as far from the 2 kg mass as from the 4 kg mass.</div></div><div class=\"ex\"><div class=\"exh\">Worked example 2 · Choosing the system</div><div class=\"exl\">A car (1000 kg) tows a trailer (500 kg); the road gives a net external force of 3000 N.<br>System car + trailer: a = 3000 ÷ 1500 = 2 m/s²; the tow bar force is internal.<br>System trailer only: the tow bar force is external and equals 500 × 2 = <b>1000 N</b>.</div></div><div class=\"keybox\"><b>Internal forces cannot move the centre of mass.</b> You cannot lift yourself by pulling on your own hair; a skater on frictionless ice cannot start moving without pushing on something outside herself.</div><div class=\"hub-btns\" style=\"margin-top:12px\"><button class=\"hub-btn primary\" data-go=\"s1\">Practise 2.1.A →</button><button class=\"hub-btn primary\" data-go=\"s2\">Practise 2.1.B →</button></div></section><section class=\"note\" id=\"n22\"><h2>Topic 2.2 · Forces and Free-Body Diagrams</h2><p class=\"lt\"><b>Learning objectives</b></p><ul class=\"lt\"><li><b>2.2.A</b> Describe a force as an interaction between two objects or systems.</li><li><b>2.2.B</b> Describe the forces exerted on an object or system using a free-body diagram.</li></ul><p>A <b>force</b> is a vector that describes an <b>interaction between two objects</b>: something pushes or pulls on something else. Every force has an object that exerts it and an object it is exerted on. Forces are <b>contact forces</b> (normal, friction, tension, spring) or <b>field (non-contact) forces</b> (gravitational, electric, magnetic). At the microscopic level contact forces come from electric interactions between the atoms of the surfaces.</p><p>The SI unit of force is the newton: 1 N = 1 kg·m/s². Forces add as vectors; the vector sum is the <b>net force</b> ΣF.</p><h4>Free-body diagrams</h4><p>A free-body diagram (FBD) shows <b>only</b> the forces exerted <i>on</i> the chosen object or system. Draw the object as a dot, draw each force as an arrow starting at the dot and pointing in its direction, make lengths roughly proportional to size, and label each force with its type and the object exerting it (F<sub>g</sub>, F<sub>N</sub>, F<sub>T</sub>, F<sub>f</sub>). Never draw velocity, acceleration or “ma” on an FBD.</p><div class=\"fig\"><svg class=\"figsvg\" viewBox=\"0 0 200 170\" role=\"img\"><defs><marker id=\"ah\" viewBox=\"0 0 10 10\" refX=\"9\" refY=\"5\" markerWidth=\"7\" markerHeight=\"7\" orient=\"auto\"><path d=\"M0,1 L10,5 L0,9 z\" class=\"ahd\"/></marker><marker id=\"ahs\" viewBox=\"0 0 10 10\" refX=\"1\" refY=\"5\" markerWidth=\"7\" markerHeight=\"7\" orient=\"auto\"><path d=\"M10,1 L0,5 L10,9 z\" class=\"ahd\"/></marker></defs><line style=\"stroke:var(--accent-text);stroke-width:2.2\" x1=\"100.0\" y1=\"85.0\" x2=\"100.0\" y2=\"30.0\" marker-end=\"url(#ah)\"/><text class=\"lb\" x=\"100.0\" y=\"15.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">F<tspan baseline-shift=\"sub\" font-size=\"9\">N</tspan></text><line style=\"stroke:var(--accent-text);stroke-width:2.2\" x1=\"100.0\" y1=\"85.0\" x2=\"100.0\" y2=\"140.0\" marker-end=\"url(#ah)\"/><text class=\"lb\" x=\"100.0\" y=\"155.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">F<tspan baseline-shift=\"sub\" font-size=\"9\">g</tspan></text><circle cx=\"100.0\" cy=\"85.0\" r=\"5\" style=\"fill:var(--ink)\"/></svg></div><p>A book at rest on a table: weight down, normal force up, equal lengths.</p><div class=\"fig\"><svg class=\"figsvg\" viewBox=\"0 0 260 180\" role=\"img\"><defs><marker id=\"ah\" viewBox=\"0 0 10 10\" refX=\"9\" refY=\"5\" markerWidth=\"7\" markerHeight=\"7\" orient=\"auto\"><path d=\"M0,1 L10,5 L0,9 z\" class=\"ahd\"/></marker><marker id=\"ahs\" viewBox=\"0 0 10 10\" refX=\"1\" refY=\"5\" markerWidth=\"7\" markerHeight=\"7\" orient=\"auto\"><path d=\"M10,1 L0,5 L10,9 z\" class=\"ahd\"/></marker></defs><line style=\"stroke:var(--accent-text);stroke-width:2.2\" x1=\"130.0\" y1=\"90.0\" x2=\"130.0\" y2=\"40.0\" marker-end=\"url(#ah)\"/><text class=\"lb\" x=\"130.0\" y=\"25.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">F<tspan baseline-shift=\"sub\" font-size=\"9\">N</tspan></text><line style=\"stroke:var(--accent-text);stroke-width:2.2\" x1=\"130.0\" y1=\"90.0\" x2=\"130.0\" y2=\"140.0\" marker-end=\"url(#ah)\"/><text class=\"lb\" x=\"130.0\" y=\"155.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">F<tspan baseline-shift=\"sub\" font-size=\"9\">g</tspan></text><line style=\"stroke:var(--accent-text);stroke-width:2.2\" x1=\"130.0\" y1=\"90.0\" x2=\"190.0\" y2=\"90.0\" marker-end=\"url(#ah)\"/><text class=\"lb\" x=\"205.0\" y=\"90.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">F<tspan baseline-shift=\"sub\" font-size=\"9\">T</tspan></text><line style=\"stroke:var(--accent-text);stroke-width:2.2\" x1=\"130.0\" y1=\"90.0\" x2=\"90.0\" y2=\"90.0\" marker-end=\"url(#ah)\"/><text class=\"lb\" x=\"75.0\" y=\"90.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">F<tspan baseline-shift=\"sub\" font-size=\"9\">f</tspan></text><circle cx=\"130.0\" cy=\"90.0\" r=\"5\" style=\"fill:var(--ink)\"/></svg></div><p>A box pulled at constant velocity by a horizontal rope over a rough floor: four forces, balanced in pairs.</p><h4>Choosing axes</h4><p>Choose axes so that one axis lies along the acceleration. On an incline of angle θ use axes along and perpendicular to the surface; the gravitational force then has components <span class=\"mono\">mg sin θ</span> down the slope and <span class=\"mono\">mg cos θ</span> into the slope.</p><div class=\"fig\"><svg class=\"figsvg\" viewBox=\"0 0 280 170\" role=\"img\"><defs><marker id=\"ah\" viewBox=\"0 0 10 10\" refX=\"9\" refY=\"5\" markerWidth=\"7\" markerHeight=\"7\" orient=\"auto\"><path d=\"M0,1 L10,5 L0,9 z\" class=\"ahd\"/></marker><marker id=\"ahs\" viewBox=\"0 0 10 10\" refX=\"1\" refY=\"5\" markerWidth=\"7\" markerHeight=\"7\" orient=\"auto\"><path d=\"M10,1 L0,5 L10,9 z\" class=\"ahd\"/></marker></defs><path d=\"M20,156 L260.0,156 L260.0,17.4 Z\" style=\"fill:var(--paper-2);stroke:var(--ink);stroke-width:1.5\"/><path class=\"wg\" d=\"M20.0,156.0 L50.0,156.0 A30,30 0 0 0 46.0,141.0 Z\"/><text class=\"al\" x=\"62.5\" y=\"144.6\" text-anchor=\"middle\" dominant-baseline=\"middle\">θ</text><path class=\"ra\" d=\"M260.0,147.0 L251.0,147.0 L251.0,156.0\"/><g transform=\"translate(152.0,79.8) rotate(-30)\"><rect x=\"-17\" y=\"-30\" width=\"34\" height=\"30\" style=\"fill:var(--gold-soft);stroke:var(--ink);stroke-width:1.3\"/><text class=\"lb\" x=\"0\" y=\"-15\" text-anchor=\"middle\" dominant-baseline=\"middle\"></text></g><line style=\"stroke:var(--danger);stroke-width:2.2\" x1=\"144.5\" y1=\"66.8\" x2=\"144.5\" y2=\"116.8\" marker-end=\"url(#ah)\"/><text class=\"lb\" x=\"144.5\" y=\"130.8\" text-anchor=\"middle\" dominant-baseline=\"middle\">mg</text><line style=\"stroke:var(--danger);stroke-width:2.2\" x1=\"144.5\" y1=\"66.8\" x2=\"119.5\" y2=\"23.5\" marker-end=\"url(#ah)\"/><text class=\"lb\" x=\"112.5\" y=\"11.4\" text-anchor=\"middle\" dominant-baseline=\"middle\">F<tspan baseline-shift=\"sub\" font-size=\"9\">N</tspan></text></svg></div><div class=\"ex\"><div class=\"exh\">Worked example 1 · Resolving on a ramp</div><div class=\"exl\">A 6.0 kg box on a smooth 30° ramp.<br>Along the ramp: 60 sin 30° = <b>30 N</b>. Into the ramp: 60 cos 30° ≈ 52 N, so F<sub>N</sub> ≈ <b>52 N</b>.</div></div><div class=\"ex\"><div class=\"exh\">Worked example 2 · Angled pull</div><div class=\"exl\">A trolley is pulled with 40 N at 37° above the horizontal.<br>Horizontal component 40 cos 37° ≈ 32 N; vertical component 40 sin 37° ≈ 24 N, which reduces the normal force by 24 N.</div></div><div class=\"keybox\"><b>There is no “force of motion”.</b> A ball flying through the air has only the gravitational force on it (ignoring air); the kick stopped when the foot lost contact.</div><div class=\"hub-btns\" style=\"margin-top:12px\"><button class=\"hub-btn primary\" data-go=\"s3\">Practise 2.2.A →</button><button class=\"hub-btn primary\" data-go=\"s4\">Practise 2.2.B →</button></div></section><section class=\"note\" id=\"n23\"><h2>Topic 2.3 · Newton's Third Law</h2><p class=\"lt\"><b>Learning objectives</b></p><ul class=\"lt\"><li><b>2.3.A</b> Describe the interaction of two objects using Newton's third law and a representation of paired forces exerted on each object.</li></ul><p>When object A exerts a force on object B, B exerts a force on A that is <b>equal in magnitude and opposite in direction</b>: F<sub>A on B</sub> = −F<sub>B on A</sub>. The two forces are the same type (both gravitational, both contact, …), act at the same time and act on <b>different objects</b> — so they never cancel each other.</p><p>To find the partner of a force, swap the two objects: “Earth pulls the apple down” ↔ “the apple pulls Earth up”. Equal forces do not mean equal accelerations: a = F ÷ m, so the lighter object accelerates more.</p><div class=\"fig\"><svg class=\"figsvg\" viewBox=\"0 0 260 170\" role=\"img\"><defs><marker id=\"ah\" viewBox=\"0 0 10 10\" refX=\"9\" refY=\"5\" markerWidth=\"7\" markerHeight=\"7\" orient=\"auto\"><path d=\"M0,1 L10,5 L0,9 z\" class=\"ahd\"/></marker><marker id=\"ahs\" viewBox=\"0 0 10 10\" refX=\"1\" refY=\"5\" markerWidth=\"7\" markerHeight=\"7\" orient=\"auto\"><path d=\"M10,1 L0,5 L10,9 z\" class=\"ahd\"/></marker></defs><line style=\"stroke:var(--danger);stroke-width:2.2\" x1=\"130.0\" y1=\"85.0\" x2=\"130.0\" y2=\"135.0\" marker-end=\"url(#ah)\"/><text class=\"lb\" x=\"130.0\" y=\"150.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">F<tspan baseline-shift=\"sub\" font-size=\"9\">g</tspan> (Earth on book)</text><line style=\"stroke:var(--accent-text);stroke-width:2.2\" x1=\"130.0\" y1=\"85.0\" x2=\"130.0\" y2=\"35.0\" marker-end=\"url(#ah)\"/><text class=\"lb\" x=\"130.0\" y=\"20.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">F<tspan baseline-shift=\"sub\" font-size=\"9\">N</tspan> (table on book)</text><circle cx=\"130.0\" cy=\"85.0\" r=\"5\" style=\"fill:var(--ink)\"/></svg></div><p>The weight of the book and the normal force on it are <b>not</b> a third-law pair: they act on the same object and are different types. The partner of F<sub>N</sub> is the book pushing down on the table; the partner of F<sub>g</sub> is the book pulling up on Earth.</p><div class=\"ex\"><div class=\"exh\">Worked example 1 · Skaters push apart</div><div class=\"exl\">Meera (40 kg) and Arjun (60 kg) push each other with 120 N.<br>Each feels 120 N. a<sub>Meera</sub> = 120 ÷ 40 = <b>3 m/s²</b>; a<sub>Arjun</sub> = 120 ÷ 60 = <b>2 m/s²</b>, in opposite directions.</div></div><div class=\"ex\"><div class=\"exh\">Worked example 2 · Walking</div><div class=\"exl\">Your foot pushes backwards on the ground; the ground pushes forwards on your foot (static friction). That forward external force accelerates you.</div></div><div class=\"keybox\"><b>A truck hitting a mosquito</b> exerts exactly the same size force on the mosquito as the mosquito exerts on the truck. The effects differ only because the masses differ.</div><div class=\"hub-btns\" style=\"margin-top:12px\"><button class=\"hub-btn primary\" data-go=\"s5\">Practise 2.3.A →</button></div></section><section class=\"note\" id=\"n24\"><h2>Topic 2.4 · Newton's First Law</h2><p class=\"lt\"><b>Learning objectives</b></p><ul class=\"lt\"><li><b>2.4.A</b> Describe the conditions under which a system's velocity remains constant.</li></ul><p>If the net external force on a system is zero, its velocity stays constant: it stays at rest or keeps moving in a straight line at constant speed. This is <b>translational equilibrium</b>. Conversely, if a system's velocity is constant, the net force on it must be zero. The tendency to keep the same velocity is called <b>inertia</b>; mass measures it.</p><p>The first law holds in <b>inertial reference frames</b> — frames that are not accelerating. In a braking bus you seem to be thrown forward, but in the ground frame you are simply continuing at your old velocity while the bus slows.</p><p>For equilibrium: ΣF<sub>x</sub> = 0 and ΣF<sub>y</sub> = 0.</p><div class=\"ex\"><div class=\"exh\">Worked example 1 · Steady driving</div><div class=\"exl\">A 1500 kg car cruises at a steady 25 m/s; air and road resistance total 800 N.<br>Constant velocity ⇒ ΣF = 0, so the driving force is <b>800 N</b> forward and F<sub>N</sub> = F<sub>g</sub> = <b>15 000 N</b>.</div></div><div class=\"ex\"><div class=\"exh\">Worked example 2 · Hanging sign</div><div class=\"exl\">A 4.0 kg sign hangs from two cords, each at 30° to the vertical.<br>Vertical: 2T cos 30° = 40 N, so T = 40 ÷ (2 × 0.866) ≈ <b>23 N</b>. The horizontal components cancel.</div></div><div class=\"keybox\"><b>Constant velocity does not need a forward net force.</b> A crate pushed at steady speed has the push exactly balanced by friction. A net force changes velocity; it does not maintain it.</div><div class=\"hub-btns\" style=\"margin-top:12px\"><button class=\"hub-btn primary\" data-go=\"s6\">Practise 2.4.A →</button></div></section><section class=\"note\" id=\"n25\"><h2>Topic 2.5 · Newton's Second Law</h2><p class=\"lt\"><b>Learning objectives</b></p><ul class=\"lt\"><li><b>2.5.A</b> Describe the conditions under which a system's velocity changes (single objects).</li></ul><p>If the net external force on a system is not zero, its velocity changes. The acceleration of the system's centre of mass is</p><div class=\"tscroll\"><table class=\"ttab\"><tr><th>Newton's second law</th><th>Units</th></tr><tr><td class=\"mono\">a<sub>sys</sub>&nbsp;=&nbsp;ΣF ÷ m<sub>sys</sub></td><td>m/s² = N/kg</td></tr></table></div><p>The acceleration is always in the <b>direction of the net force</b> (not necessarily the direction of the velocity). Apply the law separately along each axis.</p><h4>Method</h4><ol><li>Choose the system and draw its FBD.</li><li>Choose a positive direction along the acceleration.</li><li>Write ΣF = ma for each axis; solve.</li></ol><h4>Connected objects</h4><p>For objects linked by a light string over a light pulley, treat them first as <b>one system</b> (tension is internal) to get a; then take one object on its own to find the tension.</p><div class=\"fig\"><svg class=\"figsvg\" viewBox=\"0 0 200 200\" role=\"img\"><defs><marker id=\"ah\" viewBox=\"0 0 10 10\" refX=\"9\" refY=\"5\" markerWidth=\"7\" markerHeight=\"7\" orient=\"auto\"><path d=\"M0,1 L10,5 L0,9 z\" class=\"ahd\"/></marker><marker id=\"ahs\" viewBox=\"0 0 10 10\" refX=\"1\" refY=\"5\" markerWidth=\"7\" markerHeight=\"7\" orient=\"auto\"><path d=\"M10,1 L0,5 L10,9 z\" class=\"ahd\"/></marker></defs><line x1=\"60.0\" y1=\"8\" x2=\"140.0\" y2=\"8\" style=\"stroke:var(--ink);stroke-width:3\"/><line x1=\"100.0\" y1=\"8\" x2=\"100.0\" y2=\"34\" style=\"stroke:var(--ink);stroke-width:1.5\"/><circle cx=\"100.0\" cy=\"34\" r=\"20\" style=\"fill:var(--paper-2);stroke:var(--ink);stroke-width:1.5\"/><line x1=\"80.0\" y1=\"34\" x2=\"80.0\" y2=\"130\" style=\"stroke:var(--ink);stroke-width:1.4\"/><rect x=\"60.0\" y=\"130\" width=\"40\" height=\"34\" style=\"fill:var(--gold-soft);stroke:var(--ink);stroke-width:1.3\"/><text class=\"lb\" x=\"80.0\" y=\"147.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">3 kg</text><line x1=\"120.0\" y1=\"34\" x2=\"120.0\" y2=\"90\" style=\"stroke:var(--ink);stroke-width:1.4\"/><rect x=\"100.0\" y=\"90\" width=\"40\" height=\"34\" style=\"fill:var(--gold-soft);stroke:var(--ink);stroke-width:1.3\"/><text class=\"lb\" x=\"120.0\" y=\"107.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">2 kg</text></svg></div><div class=\"ex\"><div class=\"exh\">Worked example 1 · Atwood machine</div><div class=\"exl\">3 kg and 2 kg hang over a pulley.<br>System: a = (30 − 20) ÷ 5 = <b>2 m/s²</b>. For the 2 kg block: T − 20 = 2 × 2, T = <b>24 N</b> (between the two weights).</div></div><div class=\"fig\"><svg class=\"figsvg\" viewBox=\"0 0 300 170\" role=\"img\"><defs><marker id=\"ah\" viewBox=\"0 0 10 10\" refX=\"9\" refY=\"5\" markerWidth=\"7\" markerHeight=\"7\" orient=\"auto\"><path d=\"M0,1 L10,5 L0,9 z\" class=\"ahd\"/></marker><marker id=\"ahs\" viewBox=\"0 0 10 10\" refX=\"1\" refY=\"5\" markerWidth=\"7\" markerHeight=\"7\" orient=\"auto\"><path d=\"M10,1 L0,5 L10,9 z\" class=\"ahd\"/></marker></defs><rect x=\"10\" y=\"70\" width=\"220\" height=\"12\" style=\"fill:var(--paper-2);stroke:var(--ink);stroke-width:1.3\"/><line x1=\"30\" y1=\"82\" x2=\"30\" y2=\"164\" style=\"stroke:var(--ink);stroke-width:3\"/><line x1=\"210\" y1=\"82\" x2=\"210\" y2=\"164\" style=\"stroke:var(--ink);stroke-width:3\"/><rect x=\"80\" y=\"34\" width=\"56\" height=\"36\" style=\"fill:var(--gold-soft);stroke:var(--ink);stroke-width:1.3\"/><text class=\"lb\" x=\"108.0\" y=\"52.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">4 kg</text><circle cx=\"238\" cy=\"60\" r=\"10\" style=\"fill:var(--paper-2);stroke:var(--ink);stroke-width:1.4\"/><line x1=\"136\" y1=\"50\" x2=\"238\" y2=\"50\" style=\"stroke:var(--ink);stroke-width:1.4\"/><line x1=\"248\" y1=\"60\" x2=\"248\" y2=\"118\" style=\"stroke:var(--ink);stroke-width:1.4\"/><rect x=\"230\" y=\"118\" width=\"36\" height=\"34\" style=\"fill:var(--gold-soft);stroke:var(--ink);stroke-width:1.3\"/><text class=\"lb\" x=\"248.0\" y=\"135.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">1 kg</text></svg></div><div class=\"ex\"><div class=\"exh\">Worked example 2 · Table and pulley</div><div class=\"exl\">A 4 kg block on a smooth table is pulled by a 1 kg hanging block.<br>a = 10 ÷ 5 = <b>2 m/s²</b>; T = 4 × 2 = <b>8 N</b> — less than the hanging weight, because the hanging block accelerates downward.</div></div><div class=\"ex\"><div class=\"exh\">Worked example 3 · Smooth incline</div><div class=\"exl\">A block on a smooth 30° ramp: a = g sin 30° = <b>5 m/s²</b> down the slope, whatever its mass.</div></div><div class=\"keybox\"><b>Velocity and net force can point in different directions.</b> A ball thrown up is moving up while the net force (and acceleration) is down.</div><div class=\"hub-btns\" style=\"margin-top:12px\"><button class=\"hub-btn primary\" data-go=\"s7\">Practise 2.5.A (i) →</button><button class=\"hub-btn primary\" data-go=\"s8\">Practise 2.5.A (ii) →</button></div></section><section class=\"note\" id=\"n26\"><h2>Topic 2.6 · Gravitational Force</h2><p class=\"lt\"><b>Learning objectives</b></p><ul class=\"lt\"><li><b>2.6.A</b> Describe the gravitational interaction between two objects or systems with mass.</li><li><b>2.6.B</b> Describe the conditions under which the magnitude of a system's apparent weight is different from the magnitude of the gravitational force exerted on that system.</li><li><b>2.6.C</b> Describe inertial and gravitational mass.</li></ul><p>Every pair of objects with mass attract each other. <b>Newton's law of universal gravitation</b>: the force is proportional to each mass and inversely proportional to the square of the distance between their centres of mass:</p><div class=\"tscroll\"><table class=\"ttab\"><tr><th>Law</th><th>Notes</th></tr><tr><td class=\"mono\">F<sub>g</sub>&nbsp;=&nbsp;Gm<sub>1</sub>m<sub>2</sub> ÷ r²</td><td>G = 6.67 × 10⁻¹¹ N·m²/kg²; always attractive; equal and opposite on the two objects</td></tr><tr><td class=\"mono\">g&nbsp;=&nbsp;F<sub>g</sub> ÷ m&nbsp;=&nbsp;GM ÷ r²</td><td>gravitational field strength (N/kg = m/s²)</td></tr></table></div><p>The <b>field model</b>: a mass M sets up a gravitational field around it; another mass m in that field feels F<sub>g</sub> = mg. Near Earth's surface the field is almost uniform (g ≈ 10 N/kg) because heights of everyday objects are tiny compared with Earth's radius (6.4 × 10⁶ m). Further away g falls off as 1 ÷ r².</p><div class=\"fig\"><svg class=\"figsvg\" viewBox=\"0 0 320 230\" role=\"img\"><defs><marker id=\"ah\" viewBox=\"0 0 10 10\" refX=\"9\" refY=\"5\" markerWidth=\"7\" markerHeight=\"7\" orient=\"auto\"><path d=\"M0,1 L10,5 L0,9 z\" class=\"ahd\"/></marker><marker id=\"ahs\" viewBox=\"0 0 10 10\" refX=\"1\" refY=\"5\" markerWidth=\"7\" markerHeight=\"7\" orient=\"auto\"><path d=\"M10,1 L0,5 L10,9 z\" class=\"ahd\"/></marker></defs><line style=\"stroke:var(--rule)\" x1=\"46.0\" y1=\"196\" x2=\"46.0\" y2=\"18\"/><text class=\"po\" x=\"46.0\" y=\"209.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">0</text><line style=\"stroke:var(--rule)\" x1=\"109.5\" y1=\"196\" x2=\"109.5\" y2=\"18\"/><text class=\"po\" x=\"109.5\" y=\"209.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">1</text><line style=\"stroke:var(--rule)\" x1=\"173.0\" y1=\"196\" x2=\"173.0\" y2=\"18\"/><text class=\"po\" x=\"173.0\" y=\"209.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">2</text><line style=\"stroke:var(--rule)\" x1=\"236.5\" y1=\"196\" x2=\"236.5\" y2=\"18\"/><text class=\"po\" x=\"236.5\" y=\"209.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">3</text><line style=\"stroke:var(--rule)\" x1=\"300.0\" y1=\"196\" x2=\"300.0\" y2=\"18\"/><text class=\"po\" x=\"300.0\" y=\"209.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">4</text><line style=\"stroke:var(--rule)\" x1=\"46\" y1=\"196.0\" x2=\"300\" y2=\"196.0\"/><text class=\"po\" x=\"40.0\" y=\"196.0\" text-anchor=\"end\" dominant-baseline=\"middle\">0</text><line style=\"stroke:var(--rule)\" x1=\"46\" y1=\"160.4\" x2=\"300\" y2=\"160.4\"/><text class=\"po\" x=\"40.0\" y=\"160.4\" text-anchor=\"end\" dominant-baseline=\"middle\">2</text><line style=\"stroke:var(--rule)\" x1=\"46\" y1=\"124.8\" x2=\"300\" y2=\"124.8\"/><text class=\"po\" x=\"40.0\" y=\"124.8\" text-anchor=\"end\" dominant-baseline=\"middle\">4</text><line style=\"stroke:var(--rule)\" x1=\"46\" y1=\"89.2\" x2=\"300\" y2=\"89.2\"/><text class=\"po\" x=\"40.0\" y=\"89.2\" text-anchor=\"end\" dominant-baseline=\"middle\">6</text><line style=\"stroke:var(--rule)\" x1=\"46\" y1=\"53.6\" x2=\"300\" y2=\"53.6\"/><text class=\"po\" x=\"40.0\" y=\"53.6\" text-anchor=\"end\" dominant-baseline=\"middle\">8</text><line style=\"stroke:var(--rule)\" x1=\"46\" y1=\"18.0\" x2=\"300\" y2=\"18.0\"/><text class=\"po\" x=\"40.0\" y=\"18.0\" text-anchor=\"end\" dominant-baseline=\"middle\">10</text><line class=\"ln\" x1=\"46.0\" y1=\"196.0\" x2=\"308.0\" y2=\"196.0\" marker-end=\"url(#ah)\"/><line class=\"ln\" x1=\"46.0\" y1=\"196.0\" x2=\"46.0\" y2=\"10.0\" marker-end=\"url(#ah)\"/><text class=\"lb\" x=\"300.0\" y=\"188.0\" text-anchor=\"end\" dominant-baseline=\"middle\">r ÷ R</text><text class=\"lb\" x=\"52.0\" y=\"12.0\" text-anchor=\"start\" dominant-baseline=\"middle\">g (m/s²)</text><polyline fill=\"none\" style=\"stroke:var(--danger);stroke-width:2.2\" points=\"109.5,18.0 141.2,117.0 173.0,151.5 236.5,176.2 300.0,184.9\"/><circle cx=\"109.5\" cy=\"18.0\" r=\"3\" style=\"fill:var(--danger)\"/><circle cx=\"141.2\" cy=\"117.0\" r=\"3\" style=\"fill:var(--danger)\"/><circle cx=\"173.0\" cy=\"151.5\" r=\"3\" style=\"fill:var(--danger)\"/><circle cx=\"236.5\" cy=\"176.2\" r=\"3\" style=\"fill:var(--danger)\"/><circle cx=\"300.0\" cy=\"184.9\" r=\"3\" style=\"fill:var(--danger)\"/></svg></div><div class=\"ex\"><div class=\"exh\">Worked example 1 · Inverse square</div><div class=\"exl\">At twice Earth's radius from the centre, g = 10 ÷ 2² = <b>2.5 m/s²</b>; at 3R, 10 ÷ 9 ≈ 1.1 m/s².</div></div><h4>Apparent weight</h4><p>What a scale reads is the <b>normal (support) force</b>, called the apparent weight. It equals mg only when the system has no vertical acceleration. Up positive: F<sub>N</sub> − mg = ma, so F<sub>N</sub> = m(g + a).</p><div class=\"fig\"><svg class=\"figsvg\" viewBox=\"0 0 220 180\" role=\"img\"><defs><marker id=\"ah\" viewBox=\"0 0 10 10\" refX=\"9\" refY=\"5\" markerWidth=\"7\" markerHeight=\"7\" orient=\"auto\"><path d=\"M0,1 L10,5 L0,9 z\" class=\"ahd\"/></marker><marker id=\"ahs\" viewBox=\"0 0 10 10\" refX=\"1\" refY=\"5\" markerWidth=\"7\" markerHeight=\"7\" orient=\"auto\"><path d=\"M10,1 L0,5 L10,9 z\" class=\"ahd\"/></marker></defs><line style=\"stroke:var(--accent-text);stroke-width:2.2\" x1=\"110.0\" y1=\"90.0\" x2=\"110.0\" y2=\"28.0\" marker-end=\"url(#ah)\"/><text class=\"lb\" x=\"110.0\" y=\"13.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">F<tspan baseline-shift=\"sub\" font-size=\"9\">N</tspan> (scale)</text><line style=\"stroke:var(--accent-text);stroke-width:2.2\" x1=\"110.0\" y1=\"90.0\" x2=\"110.0\" y2=\"135.0\" marker-end=\"url(#ah)\"/><text class=\"lb\" x=\"110.0\" y=\"150.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">F<tspan baseline-shift=\"sub\" font-size=\"9\">g</tspan></text><circle cx=\"110.0\" cy=\"90.0\" r=\"5\" style=\"fill:var(--ink)\"/></svg></div><div class=\"tscroll\"><table class=\"ttab\"><tr><th>Lift</th><th>Scale reading</th></tr><tr><td>at rest or constant velocity</td><td>mg</td></tr><tr><td>accelerating upward (speeding up going up, or slowing going down)</td><td>more than mg</td></tr><tr><td>accelerating downward</td><td>less than mg</td></tr><tr><td>free fall (a = g down)</td><td>zero — “weightless”</td></tr></table></div><div class=\"ex\"><div class=\"exh\">Worked example 2 · Lift</div><div class=\"exl\">A 60 kg student stands on a scale in a lift accelerating upward at 2 m/s².<br>F<sub>N</sub> = 60(10 + 2) = <b>720 N</b>; his true weight is still 600 N.</div></div><h4>Inertial and gravitational mass</h4><p><b>Inertial mass</b> measures resistance to acceleration (m = F<sub>net</sub> ÷ a). <b>Gravitational mass</b> measures how strongly an object takes part in gravitational interactions (what a pan balance compares). Every experiment so far shows they are <b>equivalent</b>; that is why all objects fall with the same acceleration in a vacuum.</p><div class=\"keybox\"><b>Astronauts in orbit are not beyond gravity.</b> At the ISS g is still about 9 N/kg; they feel weightless because they and the station are falling together, so the floor exerts no normal force.</div><div class=\"hub-btns\" style=\"margin-top:12px\"><button class=\"hub-btn primary\" data-go=\"s9\">Practise 2.6.A →</button><button class=\"hub-btn primary\" data-go=\"s10\">Practise 2.6.B →</button><button class=\"hub-btn primary\" data-go=\"s11\">Practise 2.6.C →</button></div></section><section class=\"note\" id=\"n27\"><h2>Topic 2.7 · Kinetic and Static Friction</h2><p class=\"lt\"><b>Learning objectives</b></p><ul class=\"lt\"><li><b>2.7.A</b> Describe kinetic friction between two surfaces.</li><li><b>2.7.B</b> Describe static friction between two surfaces.</li></ul><p>Friction is the component of the surface's contact force <b>parallel</b> to the surface; the normal force is the perpendicular component. Friction opposes the <b>relative motion</b> (or attempted relative motion) of the two surfaces. It comes from electric interactions between the atoms of the surfaces.</p><div class=\"tscroll\"><table class=\"ttab\"><tr><th>Type</th><th>When</th><th>Size</th></tr><tr><td>kinetic</td><td>surfaces slide over each other</td><td class=\"mono\">F<sub>f,k</sub>&nbsp;=&nbsp;μ<sub>k</sub>F<sub>N</sub></td></tr><tr><td>static</td><td>no sliding</td><td class=\"mono\">F<sub>f,s</sub> ≤ μ<sub>s</sub>F<sub>N</sub></td></tr></table></div><p>μ<sub>k</sub> and μ<sub>s</sub> are dimensionless and depend on the two materials (and their condition: wet, oily, polished), not on area or speed in this model. Usually μ<sub>s</sub> &gt; μ<sub>k</sub>, so it is harder to start something sliding than to keep it sliding. Static friction is <b>as large as it needs to be</b> to prevent slipping, up to its maximum μ<sub>s</sub>F<sub>N</sub>.</p><div class=\"fig\"><svg class=\"figsvg\" viewBox=\"0 0 320 230\" role=\"img\"><defs><marker id=\"ah\" viewBox=\"0 0 10 10\" refX=\"9\" refY=\"5\" markerWidth=\"7\" markerHeight=\"7\" orient=\"auto\"><path d=\"M0,1 L10,5 L0,9 z\" class=\"ahd\"/></marker><marker id=\"ahs\" viewBox=\"0 0 10 10\" refX=\"1\" refY=\"5\" markerWidth=\"7\" markerHeight=\"7\" orient=\"auto\"><path d=\"M10,1 L0,5 L10,9 z\" class=\"ahd\"/></marker></defs><line style=\"stroke:var(--rule)\" x1=\"46.0\" y1=\"196\" x2=\"46.0\" y2=\"18\"/><text class=\"po\" x=\"46.0\" y=\"209.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">0</text><line style=\"stroke:var(--rule)\" x1=\"96.8\" y1=\"196\" x2=\"96.8\" y2=\"18\"/><text class=\"po\" x=\"96.8\" y=\"209.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">10</text><line style=\"stroke:var(--rule)\" x1=\"147.6\" y1=\"196\" x2=\"147.6\" y2=\"18\"/><text class=\"po\" x=\"147.6\" y=\"209.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">20</text><line style=\"stroke:var(--rule)\" x1=\"198.4\" y1=\"196\" x2=\"198.4\" y2=\"18\"/><text class=\"po\" x=\"198.4\" y=\"209.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">30</text><line style=\"stroke:var(--rule)\" x1=\"249.2\" y1=\"196\" x2=\"249.2\" y2=\"18\"/><text class=\"po\" x=\"249.2\" y=\"209.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">40</text><line style=\"stroke:var(--rule)\" x1=\"300.0\" y1=\"196\" x2=\"300.0\" y2=\"18\"/><text class=\"po\" x=\"300.0\" y=\"209.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">50</text><line style=\"stroke:var(--rule)\" x1=\"46\" y1=\"196.0\" x2=\"300\" y2=\"196.0\"/><text class=\"po\" x=\"40.0\" y=\"196.0\" text-anchor=\"end\" dominant-baseline=\"middle\">0</text><line style=\"stroke:var(--rule)\" x1=\"46\" y1=\"151.5\" x2=\"300\" y2=\"151.5\"/><text class=\"po\" x=\"40.0\" y=\"151.5\" text-anchor=\"end\" dominant-baseline=\"middle\">10</text><line style=\"stroke:var(--rule)\" x1=\"46\" y1=\"107.0\" x2=\"300\" y2=\"107.0\"/><text class=\"po\" x=\"40.0\" y=\"107.0\" text-anchor=\"end\" dominant-baseline=\"middle\">20</text><line style=\"stroke:var(--rule)\" x1=\"46\" y1=\"62.5\" x2=\"300\" y2=\"62.5\"/><text class=\"po\" x=\"40.0\" y=\"62.5\" text-anchor=\"end\" dominant-baseline=\"middle\">30</text><line style=\"stroke:var(--rule)\" x1=\"46\" y1=\"18.0\" x2=\"300\" y2=\"18.0\"/><text class=\"po\" x=\"40.0\" y=\"18.0\" text-anchor=\"end\" dominant-baseline=\"middle\">40</text><line class=\"ln\" x1=\"46.0\" y1=\"196.0\" x2=\"308.0\" y2=\"196.0\" marker-end=\"url(#ah)\"/><line class=\"ln\" x1=\"46.0\" y1=\"196.0\" x2=\"46.0\" y2=\"10.0\" marker-end=\"url(#ah)\"/><text class=\"lb\" x=\"300.0\" y=\"188.0\" text-anchor=\"end\" dominant-baseline=\"middle\">F_push (N)</text><text class=\"lb\" x=\"52.0\" y=\"12.0\" text-anchor=\"start\" dominant-baseline=\"middle\">F_f (N)</text><polyline fill=\"none\" style=\"stroke:var(--danger);stroke-width:2.2\" points=\"46.0,196.0 198.4,62.5 198.4,107.0 300.0,107.0\"/><circle cx=\"46.0\" cy=\"196.0\" r=\"3\" style=\"fill:var(--danger)\"/><circle cx=\"198.4\" cy=\"62.5\" r=\"3\" style=\"fill:var(--danger)\"/><circle cx=\"198.4\" cy=\"107.0\" r=\"3\" style=\"fill:var(--danger)\"/><circle cx=\"300.0\" cy=\"107.0\" r=\"3\" style=\"fill:var(--danger)\"/></svg></div><p>Friction on a 5 kg block (μ<sub>s</sub> = 0.6, μ<sub>k</sub> = 0.4) as the push increases: static friction matches the push up to 30 N, then the block slides and friction drops to 20 N.</p><div class=\"ex\"><div class=\"exh\">Worked example 1 · Sliding to a stop</div><div class=\"exl\">A 2.0 kg puck at 8 m/s slides on a floor with μ<sub>k</sub> = 0.20.<br>F<sub>f</sub> = 0.20 × 20 = 4 N; a = −2 m/s²; distance = 64 ÷ 4 = <b>16 m</b>.</div></div><div class=\"ex\"><div class=\"exh\">Worked example 2 · Crate on a lorry</div><div class=\"exl\">μ<sub>s</sub> = 0.35 between a crate and a lorry bed.<br>Static friction is the only horizontal force on the crate, so a<sub>max</sub> = μ<sub>s</sub>g = <b>3.5 m/s²</b>; if the lorry accelerates faster, the crate slides.</div></div><div class=\"ex\"><div class=\"exh\">Worked example 3 · Just slipping</div><div class=\"exl\">A block on a ramp starts to slide when the ramp reaches θ. Then mg sin θ = μ<sub>s</sub>mg cos θ, so μ<sub>s</sub> = <b>tan θ</b>.</div></div><div class=\"keybox\"><b>F<sub>N</sub> is not always mg.</b> Pulling upward at an angle, being on a ramp, or pressing down all change F<sub>N</sub> — and so change friction.</div><div class=\"hub-btns\" style=\"margin-top:12px\"><button class=\"hub-btn primary\" data-go=\"s12\">Practise 2.7.A →</button><button class=\"hub-btn primary\" data-go=\"s13\">Practise 2.7.B →</button></div></section><section class=\"note\" id=\"n28\"><h2>Topic 2.8 · Spring Forces</h2><p class=\"lt\"><b>Learning objectives</b></p><ul class=\"lt\"><li><b>2.8.A</b> Describe the force exerted on an object by an ideal spring.</li></ul><p>An <b>ideal spring</b> has negligible mass and obeys <b>Hooke's law</b>: the force it exerts is proportional to its displacement from its natural (relaxed) length and points back towards that length:</p><div class=\"tscroll\"><table class=\"ttab\"><tr><th>Hooke's law</th><th>Meaning</th></tr><tr><td class=\"mono\">F<sub>s</sub>&nbsp;=&nbsp;−kΔx</td><td>k = spring constant (N/m); minus sign: restoring force</td></tr><tr><td class=\"mono\">k<sub>eq</sub>&nbsp;=&nbsp;k<sub>1</sub> + k<sub>2</sub></td><td>springs side by side (parallel)</td></tr><tr><td class=\"mono\">1 ÷ k<sub>eq</sub>&nbsp;=&nbsp;1 ÷ k<sub>1</sub> + 1 ÷ k<sub>2</sub></td><td>springs end to end (series)</td></tr></table></div><p>A graph of |F| against |Δx| is a straight line through the origin; its <b>slope is k</b>. A stiffer spring has a larger k.</p><div class=\"fig\"><svg class=\"figsvg\" viewBox=\"0 0 320 230\" role=\"img\"><defs><marker id=\"ah\" viewBox=\"0 0 10 10\" refX=\"9\" refY=\"5\" markerWidth=\"7\" markerHeight=\"7\" orient=\"auto\"><path d=\"M0,1 L10,5 L0,9 z\" class=\"ahd\"/></marker><marker id=\"ahs\" viewBox=\"0 0 10 10\" refX=\"1\" refY=\"5\" markerWidth=\"7\" markerHeight=\"7\" orient=\"auto\"><path d=\"M10,1 L0,5 L10,9 z\" class=\"ahd\"/></marker></defs><line style=\"stroke:var(--rule)\" x1=\"46.0\" y1=\"196\" x2=\"46.0\" y2=\"18\"/><text class=\"po\" x=\"46.0\" y=\"209.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">0</text><line style=\"stroke:var(--rule)\" x1=\"109.5\" y1=\"196\" x2=\"109.5\" y2=\"18\"/><text class=\"po\" x=\"109.5\" y=\"209.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">0.02</text><line style=\"stroke:var(--rule)\" x1=\"173.0\" y1=\"196\" x2=\"173.0\" y2=\"18\"/><text class=\"po\" x=\"173.0\" y=\"209.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">0.04</text><line style=\"stroke:var(--rule)\" x1=\"236.5\" y1=\"196\" x2=\"236.5\" y2=\"18\"/><text class=\"po\" x=\"236.5\" y=\"209.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">0.06</text><line style=\"stroke:var(--rule)\" x1=\"300.0\" y1=\"196\" x2=\"300.0\" y2=\"18\"/><text class=\"po\" x=\"300.0\" y=\"209.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">0.08</text><line style=\"stroke:var(--rule)\" x1=\"46\" y1=\"196.0\" x2=\"300\" y2=\"196.0\"/><text class=\"po\" x=\"40.0\" y=\"196.0\" text-anchor=\"end\" dominant-baseline=\"middle\">0</text><line style=\"stroke:var(--rule)\" x1=\"46\" y1=\"160.4\" x2=\"300\" y2=\"160.4\"/><text class=\"po\" x=\"40.0\" y=\"160.4\" text-anchor=\"end\" dominant-baseline=\"middle\">1</text><line style=\"stroke:var(--rule)\" x1=\"46\" y1=\"124.8\" x2=\"300\" y2=\"124.8\"/><text class=\"po\" x=\"40.0\" y=\"124.8\" text-anchor=\"end\" dominant-baseline=\"middle\">2</text><line style=\"stroke:var(--rule)\" x1=\"46\" y1=\"89.2\" x2=\"300\" y2=\"89.2\"/><text class=\"po\" x=\"40.0\" y=\"89.2\" text-anchor=\"end\" dominant-baseline=\"middle\">3</text><line style=\"stroke:var(--rule)\" x1=\"46\" y1=\"53.6\" x2=\"300\" y2=\"53.6\"/><text class=\"po\" x=\"40.0\" y=\"53.6\" text-anchor=\"end\" dominant-baseline=\"middle\">4</text><line style=\"stroke:var(--rule)\" x1=\"46\" y1=\"18.0\" x2=\"300\" y2=\"18.0\"/><text class=\"po\" x=\"40.0\" y=\"18.0\" text-anchor=\"end\" dominant-baseline=\"middle\">5</text><line class=\"ln\" x1=\"46.0\" y1=\"196.0\" x2=\"308.0\" y2=\"196.0\" marker-end=\"url(#ah)\"/><line class=\"ln\" x1=\"46.0\" y1=\"196.0\" x2=\"46.0\" y2=\"10.0\" marker-end=\"url(#ah)\"/><text class=\"lb\" x=\"300.0\" y=\"188.0\" text-anchor=\"end\" dominant-baseline=\"middle\">Δx (m)</text><text class=\"lb\" x=\"52.0\" y=\"12.0\" text-anchor=\"start\" dominant-baseline=\"middle\">F (N)</text><polyline fill=\"none\" style=\"stroke:var(--danger);stroke-width:2.2\" points=\"46.0,196.0 109.5,160.4 173.0,124.8 236.5,89.2 300.0,53.6\"/><circle cx=\"46.0\" cy=\"196.0\" r=\"3\" style=\"fill:var(--danger)\"/><circle cx=\"109.5\" cy=\"160.4\" r=\"3\" style=\"fill:var(--danger)\"/><circle cx=\"173.0\" cy=\"124.8\" r=\"3\" style=\"fill:var(--danger)\"/><circle cx=\"236.5\" cy=\"89.2\" r=\"3\" style=\"fill:var(--danger)\"/><circle cx=\"300.0\" cy=\"53.6\" r=\"3\" style=\"fill:var(--danger)\"/></svg></div><div class=\"fig\"><svg class=\"figsvg\" viewBox=\"0 0 300 110\" role=\"img\"><defs><marker id=\"ah\" viewBox=\"0 0 10 10\" refX=\"9\" refY=\"5\" markerWidth=\"7\" markerHeight=\"7\" orient=\"auto\"><path d=\"M0,1 L10,5 L0,9 z\" class=\"ahd\"/></marker><marker id=\"ahs\" viewBox=\"0 0 10 10\" refX=\"1\" refY=\"5\" markerWidth=\"7\" markerHeight=\"7\" orient=\"auto\"><path d=\"M10,1 L0,5 L10,9 z\" class=\"ahd\"/></marker></defs><line x1=\"14\" y1=\"20\" x2=\"14\" y2=\"86\" style=\"stroke:var(--ink);stroke-width:3\"/><line x1=\"10\" y1=\"86\" x2=\"290\" y2=\"86\" style=\"stroke:var(--ink);stroke-width:1.5\"/><polyline points=\"14,60 40,50 52,70 64,50 76,70 88,50 100,70 112,50 124,70 136,50 148,70 160,50 172,70 190,60\" style=\"fill:none;stroke:var(--accent-text);stroke-width:2\"/><rect x=\"190\" y=\"36\" width=\"50\" height=\"50\" style=\"fill:var(--gold-soft);stroke:var(--ink);stroke-width:1.3\"/><text class=\"lb\" x=\"215.0\" y=\"61.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">m</text><text class=\"lb\" x=\"110.0\" y=\"36.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">k</text></svg></div><div class=\"ex\"><div class=\"exh\">Worked example 1 · Finding k</div><div class=\"exl\">A 0.40 kg mass hangs at rest and stretches a spring by 0.080 m.<br>kΔx = mg: k = 4.0 ÷ 0.080 = <b>50 N/m</b>.</div></div><div class=\"ex\"><div class=\"exh\">Worked example 2 · Compressed spring</div><div class=\"exl\">A spring of k = 300 N/m is compressed by 0.05 m.<br>|F| = 300 × 0.05 = <b>15 N</b>, pushing outward (towards its natural length).</div></div><div class=\"keybox\"><b>Δx is the change from the natural length</b>, not the total length. A 20 cm spring stretched to 26 cm has Δx = 6 cm = 0.06 m.</div><div class=\"hub-btns\" style=\"margin-top:12px\"><button class=\"hub-btn primary\" data-go=\"s14\">Practise 2.8.A →</button></div></section><section class=\"note\" id=\"n29\"><h2>Topic 2.9 · Circular Motion</h2><p class=\"lt\"><b>Learning objectives</b></p><ul class=\"lt\"><li><b>2.9.A</b> Describe the motion of an object traveling in a circular path.</li><li><b>2.9.B</b> Describe circular orbits using Kepler's third law.</li></ul><p>An object moving in a circle at constant speed (uniform circular motion) is <b>accelerating</b> because the direction of its velocity keeps changing. The velocity is tangent to the circle; the acceleration points to the centre (<b>centripetal</b>).</p><div class=\"fig\"><svg class=\"figsvg\" viewBox=\"0 0 230 200\" role=\"img\"><defs><marker id=\"ah\" viewBox=\"0 0 10 10\" refX=\"9\" refY=\"5\" markerWidth=\"7\" markerHeight=\"7\" orient=\"auto\"><path d=\"M0,1 L10,5 L0,9 z\" class=\"ahd\"/></marker><marker id=\"ahs\" viewBox=\"0 0 10 10\" refX=\"1\" refY=\"5\" markerWidth=\"7\" markerHeight=\"7\" orient=\"auto\"><path d=\"M10,1 L0,5 L10,9 z\" class=\"ahd\"/></marker></defs><circle cx=\"115.0\" cy=\"106.0\" r=\"70\" style=\"fill:none;stroke:var(--ink);stroke-width:1.3;stroke-dasharray:5 4\"/><line class=\"ln\" x1=\"115.0\" y1=\"106.0\" x2=\"175.6\" y2=\"71.0\"/><text class=\"lb\" x=\"137.5\" y=\"79.2\" text-anchor=\"middle\" dominant-baseline=\"middle\">r</text><line style=\"stroke:var(--danger);stroke-width:2.2\" x1=\"175.6\" y1=\"71.0\" x2=\"146.6\" y2=\"20.8\" marker-end=\"url(#ah)\"/><text class=\"lb\" x=\"139.6\" y=\"8.6\" text-anchor=\"middle\" dominant-baseline=\"middle\">v</text><line style=\"stroke:var(--success);stroke-width:2.2\" x1=\"175.6\" y1=\"71.0\" x2=\"141.0\" y2=\"91.0\" marker-end=\"url(#ah)\"/><text class=\"lb\" x=\"153.3\" y=\"104.2\" text-anchor=\"middle\" dominant-baseline=\"middle\">a</text><circle cx=\"175.6\" cy=\"71.0\" r=\"7\" style=\"fill:var(--accent-text)\"/><circle cx=\"115.0\" cy=\"106.0\" r=\"3\" style=\"fill:var(--ink)\"/></svg></div><div class=\"tscroll\"><table class=\"ttab\"><tr><th>Quantity</th><th>Expression</th></tr><tr><td>centripetal acceleration</td><td class=\"mono\">a<sub>c</sub>&nbsp;=&nbsp;v² ÷ r</td></tr><tr><td>speed and period</td><td class=\"mono\">v&nbsp;=&nbsp;2πr ÷ T</td></tr><tr><td>net force toward centre</td><td class=\"mono\">ΣF<sub>c</sub>&nbsp;=&nbsp;mv² ÷ r</td></tr></table></div><p>The net force toward the centre is supplied by real forces — tension, friction, gravity, the normal force or a combination. “Centripetal force” is not an extra force to draw on an FBD. If the object also speeds up or slows down, it has a <b>tangential</b> acceleration as well, and the total acceleration is the vector sum.</p><div class=\"ex\"><div class=\"exh\">Worked example 1 · Car on a flat bend</div><div class=\"exl\">A 1200 kg car takes a 40 m radius bend at 12 m/s.<br>a<sub>c</sub> = 144 ÷ 40 = 3.6 m/s²; the static friction needed is 1200 × 3.6 = <b>4320 N</b>.</div></div><div class=\"ex\"><div class=\"exh\">Worked example 2 · Top of a vertical loop</div><div class=\"exl\">At the top, gravity and the normal force (or tension) both point down, toward the centre: F<sub>N</sub> + mg = mv² ÷ r.<br>The slowest possible speed has F<sub>N</sub> = 0: v<sub>min</sub> = √(gr). For r = 2.5 m, v<sub>min</sub> = <b>5 m/s</b>.</div></div><h4>Circular orbits</h4><p>For a satellite of mass m in a circular orbit of radius R around a body of mass M, gravity provides the centripetal force: GMm ÷ R² = mv² ÷ R. So v = √(GM ÷ R) — independent of m. Using v = 2πR ÷ T gives <b>Kepler's third law</b>:</p><div class=\"tscroll\"><table class=\"ttab\"><tr><th>Kepler's third law</th><th>Consequence</th></tr><tr><td class=\"mono\">T²&nbsp;=&nbsp;(4π² ÷ GM)R³</td><td>T² ∝ R³ for everything orbiting the same central body</td></tr></table></div><div class=\"ex\"><div class=\"exh\">Worked example 3 · Satellite</div><div class=\"exl\">For Earth, GM = 4.0 × 10¹⁴ m³/s². A satellite orbits at R = 1.0 × 10⁷ m.<br>v = √(4.0 × 10¹⁴ ÷ 1.0 × 10⁷) ≈ <b>6.3 km/s</b>; T = 2πR ÷ v ≈ 9900 s ≈ 2.8 h.<br>An orbit 4 times as large has a period 4<sup>3/2</sup> = 8 times as long.</div></div><div class=\"keybox\"><b>If the string breaks</b>, the object moves off along the tangent (first law), not outward along the radius. There is no outward “centrifugal” force in an inertial frame.</div><div class=\"hub-btns\" style=\"margin-top:12px\"><button class=\"hub-btn primary\" data-go=\"s15\">Practise 2.9.A →</button><button class=\"hub-btn primary\" data-go=\"s16\">Practise 2.9.B →</button></div></section><section class=\"note\" id=\"nsum\"><h2>Unit checklist</h2><ul><li><b>2.1.A</b> Describe the properties and interactions of a system.</li><li><b>2.1.B</b> Describe the location of a system's center of mass with respect to the system's constituent parts.</li><li><b>2.2.A</b> Describe a force as an interaction between two objects or systems.</li><li><b>2.2.B</b> Describe the forces exerted on an object or system using a free-body diagram.</li><li><b>2.3.A</b> Describe the interaction of two objects using Newton's third law and a representation of paired forces exerted on each object.</li><li><b>2.4.A</b> Describe the conditions under which a system's velocity remains constant.</li><li><b>2.5.A (i)</b> Describe the conditions under which a system's velocity changes (single objects).</li><li><b>2.5.A (ii)</b> Describe the conditions under which a system's velocity changes (connected objects, pulleys and inclines).</li><li><b>2.6.A</b> Describe the gravitational interaction between two objects or systems with mass.</li><li><b>2.6.B</b> Describe the conditions under which the magnitude of a system's apparent weight is different from the magnitude of the gravitational force exerted on that system.</li><li><b>2.6.C</b> Describe inertial and gravitational mass.</li><li><b>2.7.A</b> Describe kinetic friction between two surfaces.</li><li><b>2.7.B</b> Describe static friction between two surfaces.</li><li><b>2.8.A</b> Describe the force exerted on an object by an ideal spring.</li><li><b>2.9.A</b> Describe the motion of an object traveling in a circular path.</li><li><b>2.9.B</b> Describe circular orbits using Kepler's third law.</li></ul><div class=\"hub-btns\" style=\"margin-top:10px\"><button class=\"hub-btn\" data-go=\"s17\">Test A</button><button class=\"hub-btn\" data-go=\"s18\">Test B</button><button class=\"hub-btn\" data-go=\"s19\">Test C</button><button class=\"hub-btn\" data-go=\"s20\">Test D</button><button class=\"hub-btn primary\" data-go=\"report\">📊 Report</button></div></section>";
var REPORT = [["s17", "A", "Knowing and understanding"], ["s18", "B", "Investigating patterns"], ["s19", "C", "Communicating"], ["s20", "D", "Applying physics in real-life contexts"]];
var SECTIONS = [{"id": "s1", "label": "2.1.A", "sub": "Systems — LO 2.1.A: describe the properties and interactions of a system.", "slides": [{"kind": "mcq", "text": "In physics, a system is", "opts": ["the object or group of objects chosen for analysis", "everything in the universe", "only the objects that are moving", "always a single object"], "correct": 0, "tag": "", "sol": "We choose the system; everything else is the surroundings."}, {"kind": "mcq", "text": "A student models a car as a single point to find its acceleration along a straight road. This is valid because", "opts": ["a car has no internal parts", "all cars have the same mass", "the internal structure of the car does not affect the motion being studied", "the forces on a car always cancel"], "correct": 2, "tag": "", "sol": "A system can be treated as one object when its internal structure is not important for the question."}, {"kind": "mcq", "text": "Carts P and Q are joined by a string. If the system is P and Q together, the tension in the string is", "opts": ["a gravitational force", "an external force", "not a force", "an internal force"], "correct": 3, "tag": "", "sol": "Both objects exerting and feeling the tension are inside the system."}, {"kind": "mcq", "text": "A girl pushes a box across a floor. For the system 'box only', which force is external?", "opts": ["the girl's push on the box", "Earth's pull on the girl", "the box's push on the girl", "the box's push on the floor"], "correct": 0, "tag": "", "sol": "External forces on the system are exerted on the box by objects outside it."}, {"kind": "mcq", "text": "In which situation can the object NOT be modelled as a single point?", "opts": ["a satellite, finding its orbital period", "a diver whose body shape changes during a somersault, when asked how her arms move", "a train finding its acceleration on a straight track", "a stone dropped from a bridge, finding its fall time"], "correct": 1, "tag": "", "sol": "When the motion of the parts matters, the internal structure cannot be ignored."}, {"kind": "mcq", "text": "A skater stands at rest on perfectly frictionless ice. How can she start moving?", "opts": ["by pulling hard on her own belt", "by bending her knees", "by throwing her bag away from her", "by swinging her arms and stopping them"], "correct": 2, "tag": "", "sol": "Only an external force (here, the bag pushing back on her) changes her velocity; forces within her body are internal."}, {"kind": "mcq", "text": "Two skaters push apart. Taking both skaters as the system, the pushes are", "opts": ["internal, so the velocity of the system's centre of mass does not change", "internal, so neither skater moves", "external, so the system accelerates", "external, so the centre of mass moves"], "correct": 0, "tag": "", "sol": "Internal forces cannot change the velocity of the system's centre of mass."}, {"kind": "blank", "p": "System: a truck and the trailer it tows along a road. Classify each force (internal / external).", "tag": "", "marks": "", "flat": [{"t": "Pull of the truck on the trailer: __B1__", "a": {"B1": "internal"}, "expr": "words"}, {"t": "Friction from the road on the truck's tyres: __B1__", "a": {"B1": "external"}, "expr": "words"}, {"t": "Earth's gravitational pull on the trailer: __B1__", "a": {"B1": "external"}, "expr": "words"}, {"t": "Pull of the trailer on the truck: __B1__", "a": {"B1": "internal"}, "expr": "words"}], "sol": "Truck and trailer are both inside the system.\nThe road is outside the system.\nEarth is outside the system.\nBoth objects are inside the system."}, {"kind": "blank", "p": "A 1200 kg car tows a 400 kg trailer. The road exerts a net forward external force of 3200 N on the car–trailer system.", "tag": "", "marks": "", "flat": [{"t": "Mass of the system = __B1__ kg", "a": {"B1": "1600"}}, {"t": "Acceleration of the system = __B1__ m/s²", "a": {"B1": "2"}}, {"t": "For this system the tow-bar force is __B1__ (internal / external).", "a": {"B1": "internal"}, "expr": "words"}], "sol": "1200 + 400 = 1600 kg.\n3200 ÷ 1600 = 2 m/s².\nIt acts between two parts of the system.", "tools": ["calc"]}, {"kind": "blank", "p": "Now choose the trailer alone as the system (same motion; ignore resistance on the trailer).", "tag": "", "marks": "", "flat": [{"t": "Net force on the trailer = __B1__ N", "a": {"B1": "800"}}, {"t": "The tow-bar force is now __B1__ (internal / external).", "a": {"B1": "external"}, "expr": "words"}, {"t": "Tow-bar force on the trailer = __B1__ N", "a": {"B1": "800"}}], "sol": "400 × 2 = 800 N.\nThe car is outside this system.\nIt is the only horizontal force on the trailer: 800 N.", "tools": ["calc"]}]}, {"id": "s2", "label": "2.1.B", "sub": "Center of mass — LO 2.1.B: describe the location of a system's center of mass with respect to the system's constituent parts.", "slides": [{"kind": "mcq", "text": "Where is the centre of mass of a uniform metre rule?", "opts": ["at the 100 cm mark", "at the 50 cm mark", "it depends on how it is held", "at the 0 cm mark"], "correct": 1, "tag": "", "sol": "Uniform and symmetric: the centre of mass is at the geometric centre."}, {"kind": "mcq", "text": "A 2 kg mass is at x = 0 and a 6 kg mass at x = 4 m. The centre of mass is at", "opts": ["x = 12 m", "x = 2 m", "x = 3 m", "x = 1 m"], "correct": 2, "tag": "", "sol": "(2 × 0 + 6 × 4) ÷ 8 = 3 m.", "fig": "<svg class=\"figsvg\" viewBox=\"0 0 300 90\" role=\"img\"><defs><marker id=\"ah\" viewBox=\"0 0 10 10\" refX=\"9\" refY=\"5\" markerWidth=\"7\" markerHeight=\"7\" orient=\"auto\"><path d=\"M0,1 L10,5 L0,9 z\" class=\"ahd\"/></marker><marker id=\"ahs\" viewBox=\"0 0 10 10\" refX=\"1\" refY=\"5\" markerWidth=\"7\" markerHeight=\"7\" orient=\"auto\"><path d=\"M10,1 L0,5 L10,9 z\" class=\"ahd\"/></marker></defs><line x1=\"24\" y1=\"44\" x2=\"276\" y2=\"44\" style=\"stroke:var(--ink);stroke-width:3\"/><circle cx=\"24.0\" cy=\"44\" r=\"11\" style=\"fill:var(--gold-soft);stroke:var(--ink);stroke-width:1.3\"/><text class=\"lb\" x=\"24.0\" y=\"22.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">2 kg</text><text class=\"po\" x=\"24.0\" y=\"68.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">0 m</text><circle cx=\"276.0\" cy=\"44\" r=\"11\" style=\"fill:var(--gold-soft);stroke:var(--ink);stroke-width:1.3\"/><text class=\"lb\" x=\"276.0\" y=\"22.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">6 kg</text><text class=\"po\" x=\"276.0\" y=\"68.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">4 m</text></svg>", "tools": ["calc"]}, {"kind": "mcq", "text": "The centre of mass of a two-object system is always", "opts": ["exactly midway between them", "at the object that is moving faster", "closer to the less massive object", "closer to the more massive object"], "correct": 3, "tag": "", "sol": "It is a mass-weighted average position."}, {"kind": "mcq", "text": "Where is the centre of mass of a uniform ring (a bangle)?", "opts": ["at the centre of the ring, where there is no material", "it has no centre of mass", "at the top of the ring", "on the ring itself"], "correct": 0, "tag": "", "sol": "By symmetry it is at the centre; the centre of mass can lie outside the material."}, {"kind": "mcq", "text": "Earth (6.0 × 10²⁴ kg) and the Moon (7.3 × 10²² kg) are 3.84 × 10⁸ m apart. The centre of mass of the pair is about", "opts": ["4.6 × 10⁸ m from Earth's centre, beyond the Moon", "1.9 × 10⁸ m from Earth's centre, halfway", "4.6 × 10⁶ m from Earth's centre, inside Earth", "3.8 × 10⁸ m from Earth's centre, at the Moon"], "correct": 2, "tag": "", "sol": "x = (7.3 × 10²² × 3.84 × 10⁸) ÷ (6.073 × 10²⁴) ≈ 4.6 × 10⁶ m, less than Earth's radius (6.4 × 10⁶ m).", "tools": ["calc"]}, {"kind": "mcq", "text": "Three 1 kg masses sit at (0, 0), (6, 0) and (0, 3) m. The centre of mass is at", "opts": ["(2, 1) m", "(6, 3) m", "(3, 1.5) m", "(2, 1.5) m"], "correct": 0, "tag": "", "sol": "x = 6 ÷ 3 = 2; y = 3 ÷ 3 = 1.", "tools": ["calc"]}, {"kind": "mcq", "text": "A 3 kg ball is at x = 1 m. Where must a 1 kg ball be placed so that the centre of mass is at x = 2 m?", "opts": ["x = 4 m", "x = 3 m", "x = 2 m", "x = 5 m"], "correct": 3, "tag": "", "sol": "3 × 1 + 1 × x = 4 × 2, so x = 5 m.", "tools": ["calc"]}, {"kind": "mcq", "text": "For an L-shaped metal bracket, the centre of mass", "opts": ["is always at the corner", "is at the end of the longer arm", "may lie outside the material", "must lie inside the material"], "correct": 2, "tag": "", "sol": "Like a ring or boomerang, the centre of mass can be in empty space."}, {"kind": "blank", "p": "Two children sit on a light plank along the x-axis: Riya (30 kg) at x = 0 and Kabir (45 kg) at x = 2.5 m.", "tag": "", "marks": "", "flat": [{"t": "Total mass = __B1__ kg", "a": {"B1": "75"}}, {"t": "Σmx = __B1__ kg·m", "a": {"B1": "112.5"}}, {"t": "x_cm = __B1__ m", "a": {"B1": "1.5"}}, {"t": "The centre of mass is closer to __B1__ (Riya / Kabir).", "a": {"B1": "kabir"}, "expr": "words"}], "sol": "30 + 45 = 75 kg.\n30 × 0 + 45 × 2.5 = 112.5 kg·m.\n112.5 ÷ 75 = 1.5 m.\nHe is more massive.", "fig": "<svg class=\"figsvg\" viewBox=\"0 0 300 90\" role=\"img\"><defs><marker id=\"ah\" viewBox=\"0 0 10 10\" refX=\"9\" refY=\"5\" markerWidth=\"7\" markerHeight=\"7\" orient=\"auto\"><path d=\"M0,1 L10,5 L0,9 z\" class=\"ahd\"/></marker><marker id=\"ahs\" viewBox=\"0 0 10 10\" refX=\"1\" refY=\"5\" markerWidth=\"7\" markerHeight=\"7\" orient=\"auto\"><path d=\"M10,1 L0,5 L10,9 z\" class=\"ahd\"/></marker></defs><line x1=\"24\" y1=\"44\" x2=\"276\" y2=\"44\" style=\"stroke:var(--ink);stroke-width:3\"/><circle cx=\"24.0\" cy=\"44\" r=\"11\" style=\"fill:var(--gold-soft);stroke:var(--ink);stroke-width:1.3\"/><text class=\"lb\" x=\"24.0\" y=\"22.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">30 kg</text><text class=\"po\" x=\"24.0\" y=\"68.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">0 m</text><circle cx=\"276.0\" cy=\"44\" r=\"11\" style=\"fill:var(--gold-soft);stroke:var(--ink);stroke-width:1.3\"/><text class=\"lb\" x=\"276.0\" y=\"22.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">45 kg</text><text class=\"po\" x=\"276.0\" y=\"68.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">2.5 m</text></svg>", "tools": ["calc"]}, {"kind": "blank", "p": "Three masses on a light rod:\nm (kg): 2, 3, 5   at x (m): 0, 0.40, 1.00", "tag": "", "marks": "", "flat": [{"t": "Total mass = __B1__ kg", "a": {"B1": "10"}}, {"t": "Σmx = __B1__ kg·m", "a": {"B1": "6.2"}}, {"t": "x_cm = __B1__ m", "a": {"B1": "0.62"}}, {"t": "The 5 kg mass is moved to x = 0.60 m. New x_cm = __B1__ m", "a": {"B1": "0.42"}}], "sol": "2 + 3 + 5 = 10 kg.\n0 + 1.2 + 5.0 = 6.2 kg·m.\n6.2 ÷ 10 = 0.62 m.\n(1.2 + 3.0) ÷ 10 = 0.42 m.", "tools": ["calc"]}, {"kind": "blank", "p": "A 4 kg block is at (0, 0) m and a 1 kg block at (5, 10) m.", "tag": "", "marks": "", "flat": [{"t": "x_cm = __B1__ m", "a": {"B1": "1"}}, {"t": "y_cm = __B1__ m", "a": {"B1": "2"}}, {"t": "Distance of the centre of mass from the 4 kg block = __B1__ m", "a": {"B1": "2.24"}, "expr": "approx"}], "sol": "(0 + 5) ÷ 5 = 1 m.\n(0 + 10) ÷ 5 = 2 m.\n√(1² + 2²) ≈ 2.24 m (one fifth of the way to the 1 kg block).", "tools": ["calc"]}]}, {"id": "s3", "label": "2.2.A", "sub": "Forces as interactions — LO 2.2.A: describe a force as an interaction between two objects or systems.", "slides": [{"kind": "mcq", "text": "A force is best described as", "opts": ["the speed of an object", "a property an object carries with it", "the energy an object has", "an interaction between two objects"], "correct": 3, "tag": "", "sol": "Every force is exerted by one object on another."}, {"kind": "mcq", "text": "Which is a contact force?", "opts": ["friction from a floor on a sliding box", "Earth's gravitational pull on the Moon", "a magnet attracting a nail 2 cm away", "the electric force between two charged balloons"], "correct": 0, "tag": "", "sol": "Friction needs the surfaces to touch; the others act at a distance (field forces)."}, {"kind": "mcq", "text": "At the microscopic level, contact forces such as normal force and friction come from", "opts": ["gravitational forces between the atoms", "magnetic poles in every object", "nuclear forces", "electric forces between the atoms of the surfaces"], "correct": 3, "tag": "", "sol": "Contact forces are the large-scale result of electric interactions."}, {"kind": "mcq", "text": "A football flies through the air after being kicked (ignore air resistance). The forces on it are", "opts": ["a 'force of motion' and gravity", "no forces", "the force of the kick and gravity", "only the gravitational force from Earth"], "correct": 3, "tag": "", "sol": "The kick ended when the boot lost contact; only Earth still interacts with the ball."}, {"kind": "mcq", "text": "Forces of 30 N and 40 N act on an object at right angles. The magnitude of the net force is", "opts": ["35 N", "10 N", "50 N", "70 N"], "correct": 2, "tag": "", "sol": "√(30² + 40²) = 50 N.", "tools": ["calc"]}, {"kind": "mcq", "text": "Which unit is equal to the newton?", "opts": ["kg·m²/s²", "kg·m/s²", "kg·m/s", "kg/(m·s²)"], "correct": 1, "tag": "", "sol": "F = ma: kg × m/s²."}, {"kind": "mcq", "text": "A book rests on a table. The table exerts on the book", "opts": ["the book's weight", "a normal force perpendicular to the table surface", "a friction force along the surface", "a tension force"], "correct": 1, "tag": "", "sol": "With no sideways push there is no friction; the support force is normal (perpendicular)."}, {"kind": "mcq", "text": "Forces of 12 N east and 5 N west act on a crate. The net force is", "opts": ["13 N east", "7 N east", "7 N west", "17 N east"], "correct": 1, "tag": "", "sol": "12 − 5 = 7 N, in the direction of the larger force."}, {"kind": "blank", "p": "Name each force (gravitational / normal / friction / tension / spring).", "tag": "", "marks": "", "flat": [{"t": "A rope pulls a bucket up a well: __B1__", "a": {"B1": "tension"}, "expr": "words"}, {"t": "A floor pushes up on your feet: __B1__", "a": {"B1": "normal"}, "expr": "words", "accept": ["normalforce", "contact"]}, {"t": "Earth pulls a falling mango: __B1__", "a": {"B1": "gravitational"}, "expr": "words", "accept": ["gravity", "weight", "gravitationalforce"]}, {"t": "A mat opposes a sliding book: __B1__", "a": {"B1": "friction"}, "expr": "words", "accept": ["frictional", "kineticfriction"]}, {"t": "A stretched catapult band pulls a stone: __B1__", "a": {"B1": "spring"}, "expr": "words", "accept": ["elastic", "springforce", "tension"]}], "sol": "A rope or string exerts tension.\nPerpendicular support from a surface.\nA field force between masses.\nParallel to the surface, opposing sliding.\nA stretched elastic object obeys a spring-like law."}, {"kind": "blank", "p": "Two forces act on a sledge: 60 N east and 80 N north.", "tag": "", "marks": "", "flat": [{"t": "Magnitude of the net force = __B1__ N", "a": {"B1": "100"}}, {"t": "Direction: __B1__° north of east", "a": {"B1": "53.1"}, "expr": "approx"}], "sol": "√(60² + 80²) = 100 N.\ntan⁻¹(80 ÷ 60) ≈ 53.1°.", "tools": ["calc"]}, {"kind": "blank", "p": "Three forces act on a box along a line (right positive): 25 N right, 40 N left and 10 N right.", "tag": "", "marks": "", "flat": [{"t": "Net force = __B1__ N", "a": {"B1": "-5"}}, {"t": "The net force points __B1__ (left / right).", "a": {"B1": "left"}, "expr": "words"}], "sol": "25 − 40 + 10 = −5 N.\nNegative means left."}]}, {"id": "s4", "label": "2.2.B", "sub": "Free-body diagrams — LO 2.2.B: describe the forces exerted on an object or system using a free-body diagram.", "slides": [{"kind": "mcq", "text": "In a free-body diagram the object is drawn as", "opts": ["a box with velocity arrows", "a dot with velocity and acceleration arrows", "a dot, with each force as an arrow starting from it", "a detailed picture with its surroundings"], "correct": 2, "tag": "", "sol": "FBDs show only forces on the object, drawn from a single point."}, {"kind": "mcq", "text": "Which is the correct FBD for a book at rest on a table?", "opts": ["three arrows: F_g, F_N and the book's push on the table", "one arrow: F_g down", "two arrows: F_g down and velocity up", "two arrows of equal length: F_g down and F_N up"], "correct": 3, "tag": "", "sol": "The book's push on the table acts on the table, not on the book."}, {"kind": "mcq", "text": "A ball thrown upward is still rising (no air resistance). Its FBD shows", "opts": ["one downward arrow (gravitational force)", "no arrows", "a large upward arrow and a smaller downward arrow", "an upward arrow only"], "correct": 0, "tag": "", "sol": "No upward force acts after release; the upward velocity is not a force."}, {"kind": "mcq", "text": "A box is pulled at constant velocity across a rough floor by a horizontal rope. How many forces belong on its FBD?", "opts": ["five, including a force of motion", "two: F_T and friction", "four: F_g, F_N, F_T and friction", "three: F_g, F_N and F_T"], "correct": 2, "tag": "", "sol": "Weight, normal, tension and kinetic friction."}, {"kind": "mcq", "text": "For a block on a ramp of angle θ, the component of the gravitational force parallel to the ramp is", "opts": ["mg", "mg tan θ", "mg cos θ", "mg sin θ"], "correct": 3, "tag": "", "sol": "The angle between F_g and the perpendicular to the ramp is θ, so the parallel part is mg sin θ.", "fig": "<svg class=\"figsvg\" viewBox=\"0 0 280 170\" role=\"img\"><defs><marker id=\"ah\" viewBox=\"0 0 10 10\" refX=\"9\" refY=\"5\" markerWidth=\"7\" markerHeight=\"7\" orient=\"auto\"><path d=\"M0,1 L10,5 L0,9 z\" class=\"ahd\"/></marker><marker id=\"ahs\" viewBox=\"0 0 10 10\" refX=\"1\" refY=\"5\" markerWidth=\"7\" markerHeight=\"7\" orient=\"auto\"><path d=\"M10,1 L0,5 L10,9 z\" class=\"ahd\"/></marker></defs><path d=\"M20,156 L260.0,156 L260.0,17.4 Z\" style=\"fill:var(--paper-2);stroke:var(--ink);stroke-width:1.5\"/><path class=\"wg\" d=\"M20.0,156.0 L50.0,156.0 A30,30 0 0 0 46.0,141.0 Z\"/><text class=\"al\" x=\"62.5\" y=\"144.6\" text-anchor=\"middle\" dominant-baseline=\"middle\">θ</text><path class=\"ra\" d=\"M260.0,147.0 L251.0,147.0 L251.0,156.0\"/><g transform=\"translate(152.0,79.8) rotate(-30)\"><rect x=\"-17\" y=\"-30\" width=\"34\" height=\"30\" style=\"fill:var(--gold-soft);stroke:var(--ink);stroke-width:1.3\"/><text class=\"lb\" x=\"0\" y=\"-15\" text-anchor=\"middle\" dominant-baseline=\"middle\">m</text></g></svg>"}, {"kind": "mcq", "text": "The FBD shows the forces on a crate. The net force on it is", "opts": ["150 N", "10 N to the right", "zero", "10 N to the left"], "correct": 1, "tag": "", "sol": "Vertical forces cancel; 30 − 20 = 10 N to the right.", "fig": "<svg class=\"figsvg\" viewBox=\"0 0 260 190\" role=\"img\"><defs><marker id=\"ah\" viewBox=\"0 0 10 10\" refX=\"9\" refY=\"5\" markerWidth=\"7\" markerHeight=\"7\" orient=\"auto\"><path d=\"M0,1 L10,5 L0,9 z\" class=\"ahd\"/></marker><marker id=\"ahs\" viewBox=\"0 0 10 10\" refX=\"1\" refY=\"5\" markerWidth=\"7\" markerHeight=\"7\" orient=\"auto\"><path d=\"M10,1 L0,5 L10,9 z\" class=\"ahd\"/></marker></defs><line style=\"stroke:var(--accent-text);stroke-width:2.2\" x1=\"130.0\" y1=\"95.0\" x2=\"130.0\" y2=\"45.0\" marker-end=\"url(#ah)\"/><text class=\"lb\" x=\"130.0\" y=\"30.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">50 N</text><line style=\"stroke:var(--accent-text);stroke-width:2.2\" x1=\"130.0\" y1=\"95.0\" x2=\"130.0\" y2=\"145.0\" marker-end=\"url(#ah)\"/><text class=\"lb\" x=\"130.0\" y=\"160.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">50 N</text><line style=\"stroke:var(--accent-text);stroke-width:2.2\" x1=\"130.0\" y1=\"95.0\" x2=\"190.0\" y2=\"95.0\" marker-end=\"url(#ah)\"/><text class=\"lb\" x=\"205.0\" y=\"95.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">30 N</text><line style=\"stroke:var(--accent-text);stroke-width:2.2\" x1=\"130.0\" y1=\"95.0\" x2=\"90.0\" y2=\"95.0\" marker-end=\"url(#ah)\"/><text class=\"lb\" x=\"75.0\" y=\"95.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">20 N</text><circle cx=\"130.0\" cy=\"95.0\" r=\"5\" style=\"fill:var(--ink)\"/></svg>"}, {"kind": "mcq", "text": "A lamp hangs at rest from two cords that make angles with the ceiling. Its FBD shows", "opts": ["F_g down and two tension arrows along the cords", "two tension arrows only", "F_g up and tension down", "F_g only"], "correct": 0, "tag": "", "sol": "Each cord pulls along its own direction; the three forces balance."}, {"kind": "mcq", "text": "For a block sliding down a ramp, the most convenient axes are", "opts": ["any axes: they give the same work", "along F_g and along the velocity", "parallel and perpendicular to the ramp", "horizontal and vertical"], "correct": 2, "tag": "", "sol": "One axis along the acceleration (down the ramp) keeps a_perp = 0."}, {"kind": "blank", "p": "A 4.0 kg box sits at rest on a smooth ramp held by a string parallel to the ramp. The ramp is at 30°.", "tag": "", "marks": "", "flat": [{"t": "F_g = __B1__ N", "a": {"B1": "40"}}, {"t": "Component of F_g along the ramp = __B1__ N", "a": {"B1": "20"}}, {"t": "Component of F_g into the ramp = __B1__ N", "a": {"B1": "34.6"}, "expr": "approx"}, {"t": "Normal force = __B1__ N", "a": {"B1": "34.6"}, "expr": "approx"}, {"t": "Tension in the string = __B1__ N", "a": {"B1": "20"}}], "sol": "4.0 × 10 = 40 N.\n40 sin 30° = 20 N.\n40 cos 30° ≈ 34.6 N.\nNo acceleration perpendicular to the ramp: F_N ≈ 34.6 N.\nThe string balances the 20 N along the ramp.", "fig": "<svg class=\"figsvg\" viewBox=\"0 0 280 170\" role=\"img\"><defs><marker id=\"ah\" viewBox=\"0 0 10 10\" refX=\"9\" refY=\"5\" markerWidth=\"7\" markerHeight=\"7\" orient=\"auto\"><path d=\"M0,1 L10,5 L0,9 z\" class=\"ahd\"/></marker><marker id=\"ahs\" viewBox=\"0 0 10 10\" refX=\"1\" refY=\"5\" markerWidth=\"7\" markerHeight=\"7\" orient=\"auto\"><path d=\"M10,1 L0,5 L10,9 z\" class=\"ahd\"/></marker></defs><path d=\"M20,156 L260.0,156 L260.0,17.4 Z\" style=\"fill:var(--paper-2);stroke:var(--ink);stroke-width:1.5\"/><path class=\"wg\" d=\"M20.0,156.0 L50.0,156.0 A30,30 0 0 0 46.0,141.0 Z\"/><text class=\"al\" x=\"62.5\" y=\"144.6\" text-anchor=\"middle\" dominant-baseline=\"middle\">30°</text><path class=\"ra\" d=\"M260.0,147.0 L251.0,147.0 L251.0,156.0\"/><g transform=\"translate(152.0,79.8) rotate(-30)\"><rect x=\"-17\" y=\"-30\" width=\"34\" height=\"30\" style=\"fill:var(--gold-soft);stroke:var(--ink);stroke-width:1.3\"/><text class=\"lb\" x=\"0\" y=\"-15\" text-anchor=\"middle\" dominant-baseline=\"middle\">4.0 kg</text></g></svg>", "tools": ["calc"]}, {"kind": "blank", "p": "A 2.0 kg lantern hangs at rest from a single vertical rope.", "tag": "", "marks": "", "flat": [{"t": "F_g = __B1__ N", "a": {"B1": "20"}}, {"t": "Tension = __B1__ N", "a": {"B1": "20"}}, {"t": "On the FBD the two arrows have __B1__ lengths (equal / different).", "a": {"B1": "equal"}, "expr": "words", "accept": ["same"]}], "sol": "2.0 × 10 = 20 N.\nEquilibrium: T = F_g.\nEqual forces, equal arrows."}, {"kind": "blank", "p": "A 5.0 kg crate on a floor is pulled with a rope at 37° above the horizontal with a tension of 50 N (it does not lift off).", "tag": "", "marks": "", "flat": [{"t": "Horizontal component of tension = __B1__ N", "a": {"B1": "39.9"}, "expr": "approx"}, {"t": "Vertical component of tension = __B1__ N", "a": {"B1": "30.1"}, "expr": "approx"}, {"t": "Normal force = __B1__ N", "a": {"B1": "19.9"}, "expr": "approx"}], "sol": "50 cos 37° ≈ 39.9 N.\n50 sin 37° ≈ 30.1 N.\nF_N + 30.1 = 50, F_N ≈ 19.9 N.", "tools": ["calc"]}]}, {"id": "s5", "label": "2.3.A", "sub": "Newton's third law — LO 2.3.A: describe the interaction of two objects using Newton's third law and a representation of paired forces exerted on each object.", "slides": [{"kind": "mcq", "text": "A hammer hits a nail with a force of 500 N. The nail exerts on the hammer", "opts": ["more than 500 N", "no force", "less than 500 N, because the nail moves", "500 N in the opposite direction"], "correct": 3, "tag": "", "sol": "Third-law forces are equal in magnitude and opposite in direction."}, {"kind": "mcq", "text": "A truck collides head-on with a small car. During the collision", "opts": ["the car exerts the larger force", "the truck exerts the larger force", "the force on each vehicle has the same magnitude", "it depends on their speeds"], "correct": 2, "tag": "", "sol": "The forces are a third-law pair; the car's acceleration is larger because its mass is smaller."}, {"kind": "mcq", "text": "The third-law partner of Earth's gravitational force on a falling apple is", "opts": ["the branch's pull on the apple", "air resistance on the apple", "the normal force on the apple", "the apple's gravitational pull on Earth"], "correct": 3, "tag": "", "sol": "Swap the objects: apple on Earth, same type (gravitational)."}, {"kind": "mcq", "text": "Why don't a third-law pair of forces cancel?", "opts": ["they act at different times", "one is always larger", "they act on different objects", "they point the same way"], "correct": 2, "tag": "", "sol": "Forces cancel only when they act on the same object."}, {"kind": "mcq", "text": "A book rests on a table. Which is a third-law pair?", "opts": ["table pushes book up; Earth pulls table down", "Earth pulls book down; book pushes table down", "table pushes up on book; book pushes down on table", "Earth pulls book down; table pushes book up"], "correct": 2, "tag": "", "sol": "Same two objects, same type of force, opposite directions."}, {"kind": "mcq", "text": "When you walk forward, which force pushes you forward?", "opts": ["your momentum", "the ground's friction force on your foot", "your foot's push on the ground", "an internal force from your muscles"], "correct": 1, "tag": "", "sol": "You push the ground back; the ground pushes you forward."}, {"kind": "mcq", "text": "A 50 kg girl and a 75 kg boy on skates push off each other. The girl accelerates at 3.0 m/s². The boy accelerates at", "opts": ["4.5 m/s²", "3.0 m/s²", "1.5 m/s²", "2.0 m/s²"], "correct": 3, "tag": "", "sol": "Force on each = 50 × 3 = 150 N; boy: 150 ÷ 75 = 2.0 m/s².", "tools": ["calc"]}, {"kind": "mcq", "text": "Earth pulls a 1 kg mass with a force of 10 N. The mass pulls Earth with", "opts": ["almost zero", "10 N", "1 N", "6 × 10²⁴ N"], "correct": 1, "tag": "", "sol": "Equal and opposite; Earth's acceleration is tiny because its mass is huge."}, {"kind": "blank", "p": "Anu (40 kg) and Dev (60 kg) stand at rest on ice and push each other with a force of 120 N for 0.50 s.", "tag": "", "marks": "", "flat": [{"t": "Force on Dev = __B1__ N", "a": {"B1": "120"}}, {"t": "Anu's acceleration = __B1__ m/s²", "a": {"B1": "3"}}, {"t": "Dev's acceleration = __B1__ m/s²", "a": {"B1": "2"}}, {"t": "Anu's speed after the push = __B1__ m/s", "a": {"B1": "1.5"}}, {"t": "Dev's speed after the push = __B1__ m/s", "a": {"B1": "1"}}], "sol": "Third law: 120 N.\n120 ÷ 40 = 3 m/s².\n120 ÷ 60 = 2 m/s².\n3 × 0.50 = 1.5 m/s.\n2 × 0.50 = 1.0 m/s (opposite way).", "tools": ["calc"]}, {"kind": "blank", "p": "A 50 kg boy stands at rest on a floor.", "tag": "", "marks": "", "flat": [{"t": "Earth pulls the boy down with __B1__ N", "a": {"B1": "500"}}, {"t": "Its third-law partner is the boy's pull on __B1__ (Earth / the floor).", "a": {"B1": "earth"}, "expr": "words"}, {"t": "The floor pushes the boy up with __B1__ N", "a": {"B1": "500"}}, {"t": "Its partner is the boy's push on __B1__ (Earth / the floor).", "a": {"B1": "floor"}, "expr": "words", "accept": ["thefloor"]}], "sol": "50 × 10 = 500 N.\nGravitational pair: boy pulls Earth up with 500 N.\nEquilibrium: F_N = 500 N.\nContact pair: boy pushes floor down with 500 N."}, {"kind": "blank", "p": "A bat exerts an average force of 800 N on a 0.16 kg cricket ball.", "tag": "", "marks": "", "flat": [{"t": "Force of the ball on the bat = __B1__ N", "a": {"B1": "800"}}, {"t": "Acceleration of the ball = __B1__ m/s²", "a": {"B1": "5000"}}, {"t": "Acceleration of the 1.6 kg bat-and-hands (from this force alone) = __B1__ m/s²", "a": {"B1": "500"}}], "sol": "Third law.\n800 ÷ 0.16 = 5000 m/s².\n800 ÷ 1.6 = 500 m/s²: same force, 10 times the mass.", "tools": ["calc"]}]}, {"id": "s6", "label": "2.4.A", "sub": "Newton's first law — LO 2.4.A: describe the conditions under which a system's velocity remains constant.", "slides": [{"kind": "mcq", "text": "An object moves with constant velocity. The net force on it is", "opts": ["zero", "in the direction of motion", "opposite to the motion", "equal to its weight"], "correct": 0, "tag": "", "sol": "Constant velocity ⇔ ΣF = 0."}, {"kind": "mcq", "text": "A puck slides at 5 m/s across frictionless ice. To keep it moving at 5 m/s", "opts": ["an increasing force is needed", "a constant forward force is needed", "it will slow down anyway", "no force is needed"], "correct": 3, "tag": "", "sol": "First law: with no net force, velocity stays constant."}, {"kind": "mcq", "text": "Standing passengers lurch forward when a bus brakes suddenly because", "opts": ["a forward force pushes them", "their weight increases", "the bus pulls them forward", "their bodies tend to keep moving at the same velocity"], "correct": 3, "tag": "", "sol": "Inertia: nothing pushes them forward; the bus slows under them."}, {"kind": "mcq", "text": "A 60 kg person rides a lift moving up at a constant 2 m/s. The normal force on her is", "opts": ["zero", "480 N", "600 N", "720 N"], "correct": 2, "tag": "", "sol": "Constant velocity: F_N = mg = 600 N."}, {"kind": "mcq", "text": "A skydiver falls at a constant terminal speed. The air resistance on her is", "opts": ["zero", "greater than her weight", "equal to her weight", "less than her weight"], "correct": 2, "tag": "", "sol": "Constant velocity: forces balance."}, {"kind": "mcq", "text": "Which object is in translational equilibrium?", "opts": ["a train speeding up", "a car going round a bend at a steady speed", "a car moving at a steady 60 km/h on a straight road", "a ball at the top of its flight"], "correct": 2, "tag": "", "sol": "Only the car on the straight road at steady speed has constant velocity (magnitude and direction)."}, {"kind": "mcq", "text": "Newton's first law holds in", "opts": ["every reference frame", "rotating frames only", "reference frames that are not accelerating (inertial frames)", "the frame of a braking bus"], "correct": 2, "tag": "", "sol": "In an accelerating frame objects appear to accelerate with no net force."}, {"kind": "mcq", "text": "A crate is pushed across a floor at constant velocity with a horizontal force of 150 N. The friction on it is", "opts": ["less than 150 N", "more than 150 N", "zero", "150 N, opposite to the push"], "correct": 3, "tag": "", "sol": "Constant velocity: friction balances the push."}, {"kind": "blank", "p": "A 1200 kg car travels at a constant 20 m/s on a level road. The road's forward force on the drive wheels is 900 N.", "tag": "", "marks": "", "flat": [{"t": "Net force = __B1__ N", "a": {"B1": "0"}}, {"t": "Total resistive force = __B1__ N", "a": {"B1": "900"}}, {"t": "Normal force from the road = __B1__ N", "a": {"B1": "12000"}}], "sol": "Constant velocity: ΣF = 0.\nResistance balances the 900 N.\nF_N = mg = 12 000 N.", "tools": ["calc"]}, {"kind": "blank", "p": "A 3.0 kg picture hangs at rest from two cords, each at 30° to the vertical.", "tag": "", "marks": "", "flat": [{"t": "F_g = __B1__ N", "a": {"B1": "30"}}, {"t": "Vertical component of each tension = __B1__ N", "a": {"B1": "15"}}, {"t": "Tension in each cord = __B1__ N", "a": {"B1": "17.3"}, "expr": "approx"}, {"t": "The horizontal components of the tensions __B1__ (cancel / add).", "a": {"B1": "cancel"}, "expr": "words"}], "sol": "3.0 × 10 = 30 N.\nShared equally: 15 N each.\nT cos 30° = 15, T ≈ 17.3 N.\nEqual and opposite, so ΣF_x = 0.", "tools": ["calc"]}, {"kind": "blank", "p": "A 10 kg box rests without moving on a rough ramp at 30°.", "tag": "", "marks": "", "flat": [{"t": "Component of F_g down the ramp = __B1__ N", "a": {"B1": "50"}}, {"t": "Normal force = __B1__ N", "a": {"B1": "86.6"}, "expr": "approx"}, {"t": "Friction force = __B1__ N", "a": {"B1": "50"}}, {"t": "Friction points __B1__ the ramp (up / down).", "a": {"B1": "up"}, "expr": "words"}], "sol": "100 sin 30° = 50 N.\n100 cos 30° ≈ 86.6 N.\nEquilibrium along the ramp: 50 N.\nIt must oppose the 50 N component down the ramp.", "fig": "<svg class=\"figsvg\" viewBox=\"0 0 280 170\" role=\"img\"><defs><marker id=\"ah\" viewBox=\"0 0 10 10\" refX=\"9\" refY=\"5\" markerWidth=\"7\" markerHeight=\"7\" orient=\"auto\"><path d=\"M0,1 L10,5 L0,9 z\" class=\"ahd\"/></marker><marker id=\"ahs\" viewBox=\"0 0 10 10\" refX=\"1\" refY=\"5\" markerWidth=\"7\" markerHeight=\"7\" orient=\"auto\"><path d=\"M10,1 L0,5 L10,9 z\" class=\"ahd\"/></marker></defs><path d=\"M20,156 L260.0,156 L260.0,17.4 Z\" style=\"fill:var(--paper-2);stroke:var(--ink);stroke-width:1.5\"/><path class=\"wg\" d=\"M20.0,156.0 L50.0,156.0 A30,30 0 0 0 46.0,141.0 Z\"/><text class=\"al\" x=\"62.5\" y=\"144.6\" text-anchor=\"middle\" dominant-baseline=\"middle\">30°</text><path class=\"ra\" d=\"M260.0,147.0 L251.0,147.0 L251.0,156.0\"/><g transform=\"translate(152.0,79.8) rotate(-30)\"><rect x=\"-17\" y=\"-30\" width=\"34\" height=\"30\" style=\"fill:var(--gold-soft);stroke:var(--ink);stroke-width:1.3\"/><text class=\"lb\" x=\"0\" y=\"-15\" text-anchor=\"middle\" dominant-baseline=\"middle\">10 kg</text></g></svg>", "tools": ["calc"]}]}, {"id": "s7", "label": "2.5.A (i)", "sub": "Newton's second law — LO 2.5.A: describe the conditions under which a system's velocity changes (single objects).", "slides": [{"kind": "mcq", "text": "A 4 kg cart has a net force of 12 N on it. Its acceleration is", "opts": ["0.33 m/s²", "48 m/s²", "3 m/s²", "16 m/s²"], "correct": 2, "tag": "", "sol": "a = 12 ÷ 4 = 3 m/s².", "tools": ["calc"]}, {"kind": "mcq", "text": "The same net force acts on a cart and then on a cart of twice the mass. The second acceleration is", "opts": ["the same", "four times as large", "twice as large", "half as large"], "correct": 3, "tag": "", "sol": "a = F ÷ m."}, {"kind": "mcq", "text": "The acceleration of an object is always in the direction of", "opts": ["its velocity", "the net force", "its displacement", "the largest single force"], "correct": 1, "tag": "", "sol": "a = ΣF ÷ m is a vector equation."}, {"kind": "mcq", "text": "A 1500 kg car goes from rest to 20 m/s in 10 s. The net force on it is", "opts": ["30 000 N", "150 N", "3000 N", "750 N"], "correct": 2, "tag": "", "sol": "a = 2 m/s²; F = 1500 × 2 = 3000 N.", "tools": ["calc"]}, {"kind": "mcq", "text": "A 2 kg ball is at the top of its flight. The net force on it is", "opts": ["zero", "2 N downward", "20 N upward", "20 N downward"], "correct": 3, "tag": "", "sol": "Only gravity acts: 2 × 10 = 20 N down, even though v = 0."}, {"kind": "mcq", "text": "A 5 kg box is pulled straight up by a rope with a tension of 70 N. Its acceleration is", "opts": ["4 m/s² upward", "24 m/s² upward", "14 m/s² upward", "10 m/s² downward"], "correct": 0, "tag": "", "sol": "(70 − 50) ÷ 5 = 4 m/s².", "tools": ["calc"]}, {"kind": "mcq", "text": "A moving object has a 10 N force forward and a 10 N force backward on it. It", "opts": ["stops immediately", "speeds up", "continues at constant velocity", "slows down and stops"], "correct": 2, "tag": "", "sol": "ΣF = 0, so the velocity does not change."}, {"kind": "mcq", "text": "A 6 N net force gives object A an acceleration of 3 m/s² and object B 2 m/s². The same force on A and B together gives", "opts": ["2.5 m/s²", "1 m/s²", "1.2 m/s²", "5 m/s²"], "correct": 2, "tag": "", "sol": "m_A = 2 kg, m_B = 3 kg; 6 ÷ 5 = 1.2 m/s².", "tools": ["calc"]}, {"kind": "blank", "p": "A 2000 kg truck: engine (road) forward force 7000 N, total resistance 3000 N. It starts from rest.", "tag": "", "marks": "", "flat": [{"t": "Net force = __B1__ N", "a": {"B1": "4000"}}, {"t": "Acceleration = __B1__ m/s²", "a": {"B1": "2"}}, {"t": "Speed after 5.0 s = __B1__ m/s", "a": {"B1": "10"}}, {"t": "Distance in 5.0 s = __B1__ m", "a": {"B1": "25"}}], "sol": "7000 − 3000 = 4000 N.\n4000 ÷ 2000 = 2 m/s².\n2 × 5 = 10 m/s.\n½ × 2 × 25 = 25 m.", "tools": ["calc"]}, {"kind": "blank", "p": "A 0.50 kg ball is pulled upward by a string with a tension of 8.0 N.", "tag": "", "marks": "", "flat": [{"t": "F_g = __B1__ N", "a": {"B1": "5"}}, {"t": "Net force = __B1__ N", "a": {"B1": "3"}}, {"t": "Acceleration = __B1__ m/s²", "a": {"B1": "6"}}, {"t": "The acceleration points __B1__ (up / down).", "a": {"B1": "up"}, "expr": "words", "accept": ["upward", "upwards"]}], "sol": "0.50 × 10 = 5 N.\n8 − 5 = 3 N.\n3 ÷ 0.50 = 6 m/s².\nThe net force is upward.", "tools": ["calc"]}, {"kind": "blank", "p": "A 1000 kg car moving at 25 m/s brakes to rest in a distance of 50 m.", "tag": "", "marks": "", "flat": [{"t": "Acceleration (forward positive) = __B1__ m/s²", "a": {"B1": "-6.25"}}, {"t": "Size of the braking force = __B1__ N", "a": {"B1": "6250"}}, {"t": "The net force points __B1__ (forward / backward).", "a": {"B1": "backward"}, "expr": "words", "accept": ["backwards", "back"]}], "sol": "0 = 625 + 2a(50), a = −6.25 m/s².\n1000 × 6.25 = 6250 N.\nOpposite to the velocity, so the car slows.", "tools": ["calc"]}]}, {"id": "s8", "label": "2.5.A (ii)", "sub": "Connected objects and ramps — LO 2.5.A: describe the conditions under which a system's velocity changes (connected objects, pulleys and inclines).", "slides": [{"kind": "mcq", "text": "Blocks of 3 kg and 2 kg sit side by side on a frictionless table. A 20 N push acts on the 3 kg block. The acceleration is", "opts": ["6.7 m/s²", "2 m/s²", "10 m/s²", "4 m/s²"], "correct": 3, "tag": "", "sol": "Whole system: 20 ÷ 5 = 4 m/s².", "tools": ["calc"]}, {"kind": "mcq", "text": "Blocks of 3 kg and 2 kg sit side by side on a frictionless table. A 20 N push acts on the 3 kg block. The force of the 3 kg block on the 2 kg block is", "opts": ["8 N", "4 N", "20 N", "12 N"], "correct": 0, "tag": "", "sol": "The 2 kg block needs 2 × 4 = 8 N.", "tools": ["calc"]}, {"kind": "mcq", "text": "Masses of 3 kg and 2 kg hang over a light frictionless pulley (Atwood machine). The acceleration is", "opts": ["2 m/s²", "5 m/s²", "10 m/s²", "4 m/s²"], "correct": 0, "tag": "", "sol": "(30 − 20) ÷ 5 = 2 m/s².", "fig": "<svg class=\"figsvg\" viewBox=\"0 0 200 200\" role=\"img\"><defs><marker id=\"ah\" viewBox=\"0 0 10 10\" refX=\"9\" refY=\"5\" markerWidth=\"7\" markerHeight=\"7\" orient=\"auto\"><path d=\"M0,1 L10,5 L0,9 z\" class=\"ahd\"/></marker><marker id=\"ahs\" viewBox=\"0 0 10 10\" refX=\"1\" refY=\"5\" markerWidth=\"7\" markerHeight=\"7\" orient=\"auto\"><path d=\"M10,1 L0,5 L10,9 z\" class=\"ahd\"/></marker></defs><line x1=\"60.0\" y1=\"8\" x2=\"140.0\" y2=\"8\" style=\"stroke:var(--ink);stroke-width:3\"/><line x1=\"100.0\" y1=\"8\" x2=\"100.0\" y2=\"34\" style=\"stroke:var(--ink);stroke-width:1.5\"/><circle cx=\"100.0\" cy=\"34\" r=\"20\" style=\"fill:var(--paper-2);stroke:var(--ink);stroke-width:1.5\"/><line x1=\"80.0\" y1=\"34\" x2=\"80.0\" y2=\"130\" style=\"stroke:var(--ink);stroke-width:1.4\"/><rect x=\"60.0\" y=\"130\" width=\"40\" height=\"34\" style=\"fill:var(--gold-soft);stroke:var(--ink);stroke-width:1.3\"/><text class=\"lb\" x=\"80.0\" y=\"147.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">3 kg</text><line x1=\"120.0\" y1=\"34\" x2=\"120.0\" y2=\"90\" style=\"stroke:var(--ink);stroke-width:1.4\"/><rect x=\"100.0\" y=\"90\" width=\"40\" height=\"34\" style=\"fill:var(--gold-soft);stroke:var(--ink);stroke-width:1.3\"/><text class=\"lb\" x=\"120.0\" y=\"107.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">2 kg</text></svg>", "tools": ["calc"]}, {"kind": "mcq", "text": "A block slides down a frictionless 30° ramp. Its acceleration is", "opts": ["0", "10 m/s²", "8.7 m/s²", "5 m/s²"], "correct": 3, "tag": "", "sol": "a = g sin 30° = 5 m/s², independent of mass."}, {"kind": "mcq", "text": "A 4 kg block on a frictionless table is pulled by a 1 kg hanging block over a pulley. The acceleration is", "opts": ["10 m/s²", "0.4 m/s²", "2 m/s²", "2.5 m/s²"], "correct": 2, "tag": "", "sol": "Net external force 10 N on 5 kg.", "fig": "<svg class=\"figsvg\" viewBox=\"0 0 300 170\" role=\"img\"><defs><marker id=\"ah\" viewBox=\"0 0 10 10\" refX=\"9\" refY=\"5\" markerWidth=\"7\" markerHeight=\"7\" orient=\"auto\"><path d=\"M0,1 L10,5 L0,9 z\" class=\"ahd\"/></marker><marker id=\"ahs\" viewBox=\"0 0 10 10\" refX=\"1\" refY=\"5\" markerWidth=\"7\" markerHeight=\"7\" orient=\"auto\"><path d=\"M10,1 L0,5 L10,9 z\" class=\"ahd\"/></marker></defs><rect x=\"10\" y=\"70\" width=\"220\" height=\"12\" style=\"fill:var(--paper-2);stroke:var(--ink);stroke-width:1.3\"/><line x1=\"30\" y1=\"82\" x2=\"30\" y2=\"164\" style=\"stroke:var(--ink);stroke-width:3\"/><line x1=\"210\" y1=\"82\" x2=\"210\" y2=\"164\" style=\"stroke:var(--ink);stroke-width:3\"/><rect x=\"80\" y=\"34\" width=\"56\" height=\"36\" style=\"fill:var(--gold-soft);stroke:var(--ink);stroke-width:1.3\"/><text class=\"lb\" x=\"108.0\" y=\"52.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">4 kg</text><circle cx=\"238\" cy=\"60\" r=\"10\" style=\"fill:var(--paper-2);stroke:var(--ink);stroke-width:1.4\"/><line x1=\"136\" y1=\"50\" x2=\"238\" y2=\"50\" style=\"stroke:var(--ink);stroke-width:1.4\"/><line x1=\"248\" y1=\"60\" x2=\"248\" y2=\"118\" style=\"stroke:var(--ink);stroke-width:1.4\"/><rect x=\"230\" y=\"118\" width=\"36\" height=\"34\" style=\"fill:var(--gold-soft);stroke:var(--ink);stroke-width:1.3\"/><text class=\"lb\" x=\"248.0\" y=\"135.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">1 kg</text></svg>", "tools": ["calc"]}, {"kind": "mcq", "text": "A 4 kg block on a frictionless table is pulled by a 1 kg hanging block over a pulley. The tension in the string is", "opts": ["12 N", "8 N", "2 N", "10 N"], "correct": 1, "tag": "", "sol": "On the 4 kg block: T = 4 × 2 = 8 N."}, {"kind": "mcq", "text": "A hanging block pulls a cart across a table through a string over a pulley. While accelerating, the tension is", "opts": ["less than the weight of the hanging block", "equal to the weight of the hanging block", "zero", "greater than the weight of the hanging block"], "correct": 0, "tag": "", "sol": "The hanging block accelerates downward, so its net force is downward: T < mg."}, {"kind": "mcq", "text": "An engine pulls three identical wagons in a line on a smooth track. The coupling force between the engine and wagon 1, compared with that between wagons 2 and 3, is", "opts": ["equal", "one third as large", "3 times as large", "twice as large"], "correct": 2, "tag": "", "sol": "The first coupling accelerates 3 wagons; the last accelerates 1."}, {"kind": "blank", "p": "A 5 kg and a 3 kg block hang over a light frictionless pulley.", "tag": "", "marks": "", "flat": [{"t": "Net external force on the system = __B1__ N", "a": {"B1": "20"}}, {"t": "Total mass = __B1__ kg", "a": {"B1": "8"}}, {"t": "Acceleration = __B1__ m/s²", "a": {"B1": "2.5"}}, {"t": "Tension = __B1__ N", "a": {"B1": "37.5"}}], "sol": "50 − 30 = 20 N.\n8 kg.\n20 ÷ 8 = 2.5 m/s².\n3 kg block: T − 30 = 3 × 2.5, T = 37.5 N.", "fig": "<svg class=\"figsvg\" viewBox=\"0 0 200 200\" role=\"img\"><defs><marker id=\"ah\" viewBox=\"0 0 10 10\" refX=\"9\" refY=\"5\" markerWidth=\"7\" markerHeight=\"7\" orient=\"auto\"><path d=\"M0,1 L10,5 L0,9 z\" class=\"ahd\"/></marker><marker id=\"ahs\" viewBox=\"0 0 10 10\" refX=\"1\" refY=\"5\" markerWidth=\"7\" markerHeight=\"7\" orient=\"auto\"><path d=\"M10,1 L0,5 L10,9 z\" class=\"ahd\"/></marker></defs><line x1=\"60.0\" y1=\"8\" x2=\"140.0\" y2=\"8\" style=\"stroke:var(--ink);stroke-width:3\"/><line x1=\"100.0\" y1=\"8\" x2=\"100.0\" y2=\"34\" style=\"stroke:var(--ink);stroke-width:1.5\"/><circle cx=\"100.0\" cy=\"34\" r=\"20\" style=\"fill:var(--paper-2);stroke:var(--ink);stroke-width:1.5\"/><line x1=\"80.0\" y1=\"34\" x2=\"80.0\" y2=\"130\" style=\"stroke:var(--ink);stroke-width:1.4\"/><rect x=\"60.0\" y=\"130\" width=\"40\" height=\"34\" style=\"fill:var(--gold-soft);stroke:var(--ink);stroke-width:1.3\"/><text class=\"lb\" x=\"80.0\" y=\"147.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">5 kg</text><line x1=\"120.0\" y1=\"34\" x2=\"120.0\" y2=\"90\" style=\"stroke:var(--ink);stroke-width:1.4\"/><rect x=\"100.0\" y=\"90\" width=\"40\" height=\"34\" style=\"fill:var(--gold-soft);stroke:var(--ink);stroke-width:1.3\"/><text class=\"lb\" x=\"120.0\" y=\"107.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">3 kg</text></svg>", "tools": ["calc"]}, {"kind": "blank", "p": "A 6 kg block on a frictionless table is joined by a string over a pulley to a 2 kg hanging block.", "tag": "", "marks": "", "flat": [{"t": "Acceleration = __B1__ m/s²", "a": {"B1": "2.5"}}, {"t": "Tension = __B1__ N", "a": {"B1": "15"}}, {"t": "The tension is __B1__ than the hanging weight (less / more).", "a": {"B1": "less"}, "expr": "words"}], "sol": "20 ÷ 8 = 2.5 m/s².\n6 × 2.5 = 15 N.\n15 N < 20 N.", "fig": "<svg class=\"figsvg\" viewBox=\"0 0 300 170\" role=\"img\"><defs><marker id=\"ah\" viewBox=\"0 0 10 10\" refX=\"9\" refY=\"5\" markerWidth=\"7\" markerHeight=\"7\" orient=\"auto\"><path d=\"M0,1 L10,5 L0,9 z\" class=\"ahd\"/></marker><marker id=\"ahs\" viewBox=\"0 0 10 10\" refX=\"1\" refY=\"5\" markerWidth=\"7\" markerHeight=\"7\" orient=\"auto\"><path d=\"M10,1 L0,5 L10,9 z\" class=\"ahd\"/></marker></defs><rect x=\"10\" y=\"70\" width=\"220\" height=\"12\" style=\"fill:var(--paper-2);stroke:var(--ink);stroke-width:1.3\"/><line x1=\"30\" y1=\"82\" x2=\"30\" y2=\"164\" style=\"stroke:var(--ink);stroke-width:3\"/><line x1=\"210\" y1=\"82\" x2=\"210\" y2=\"164\" style=\"stroke:var(--ink);stroke-width:3\"/><rect x=\"80\" y=\"34\" width=\"56\" height=\"36\" style=\"fill:var(--gold-soft);stroke:var(--ink);stroke-width:1.3\"/><text class=\"lb\" x=\"108.0\" y=\"52.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">6 kg</text><circle cx=\"238\" cy=\"60\" r=\"10\" style=\"fill:var(--paper-2);stroke:var(--ink);stroke-width:1.4\"/><line x1=\"136\" y1=\"50\" x2=\"238\" y2=\"50\" style=\"stroke:var(--ink);stroke-width:1.4\"/><line x1=\"248\" y1=\"60\" x2=\"248\" y2=\"118\" style=\"stroke:var(--ink);stroke-width:1.4\"/><rect x=\"230\" y=\"118\" width=\"36\" height=\"34\" style=\"fill:var(--gold-soft);stroke:var(--ink);stroke-width:1.3\"/><text class=\"lb\" x=\"248.0\" y=\"135.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">2 kg</text></svg>", "tools": ["calc"]}, {"kind": "blank", "p": "A 2.0 kg block is released from rest on a frictionless 30° ramp.", "tag": "", "marks": "", "flat": [{"t": "Acceleration down the ramp = __B1__ m/s²", "a": {"B1": "5"}}, {"t": "Speed after sliding 2.5 m = __B1__ m/s", "a": {"B1": "5"}}, {"t": "Time to slide 2.5 m = __B1__ s", "a": {"B1": "1"}}], "sol": "g sin 30° = 5 m/s².\nv² = 2 × 5 × 2.5 = 25, v = 5 m/s.\nt = v ÷ a = 1 s.", "fig": "<svg class=\"figsvg\" viewBox=\"0 0 280 170\" role=\"img\"><defs><marker id=\"ah\" viewBox=\"0 0 10 10\" refX=\"9\" refY=\"5\" markerWidth=\"7\" markerHeight=\"7\" orient=\"auto\"><path d=\"M0,1 L10,5 L0,9 z\" class=\"ahd\"/></marker><marker id=\"ahs\" viewBox=\"0 0 10 10\" refX=\"1\" refY=\"5\" markerWidth=\"7\" markerHeight=\"7\" orient=\"auto\"><path d=\"M10,1 L0,5 L10,9 z\" class=\"ahd\"/></marker></defs><path d=\"M20,156 L260.0,156 L260.0,17.4 Z\" style=\"fill:var(--paper-2);stroke:var(--ink);stroke-width:1.5\"/><path class=\"wg\" d=\"M20.0,156.0 L50.0,156.0 A30,30 0 0 0 46.0,141.0 Z\"/><text class=\"al\" x=\"62.5\" y=\"144.6\" text-anchor=\"middle\" dominant-baseline=\"middle\">30°</text><path class=\"ra\" d=\"M260.0,147.0 L251.0,147.0 L251.0,156.0\"/><g transform=\"translate(152.0,79.8) rotate(-30)\"><rect x=\"-17\" y=\"-30\" width=\"34\" height=\"30\" style=\"fill:var(--gold-soft);stroke:var(--ink);stroke-width:1.3\"/><text class=\"lb\" x=\"0\" y=\"-15\" text-anchor=\"middle\" dominant-baseline=\"middle\">2.0 kg</text></g></svg>", "tools": ["calc"]}, {"kind": "blank", "p": "An 8 kg box and a 4 kg box are joined by a string on a frictionless floor. A 36 N horizontal pull acts on the 8 kg box, dragging the 4 kg box behind.", "tag": "", "marks": "", "flat": [{"t": "Acceleration = __B1__ m/s²", "a": {"B1": "3"}}, {"t": "Tension in the connecting string = __B1__ N", "a": {"B1": "12"}}, {"t": "Net force on the 8 kg box = __B1__ N", "a": {"B1": "24"}}], "sol": "36 ÷ 12 = 3 m/s².\n4 × 3 = 12 N.\n36 − 12 = 24 N (= 8 × 3).", "tools": ["calc"]}]}, {"id": "s9", "label": "2.6.A", "sub": "Universal gravitation — LO 2.6.A: describe the gravitational interaction between two objects or systems with mass.", "slides": [{"kind": "mcq", "text": "The distance between the centres of two spheres is doubled. The gravitational force between them becomes", "opts": ["F ÷ 4", "2F", "4F", "F ÷ 2"], "correct": 0, "tag": "", "sol": "Inverse square: 1 ÷ 2² = ¼."}, {"kind": "mcq", "text": "Both masses are doubled and the distance is unchanged. The force becomes", "opts": ["F ÷ 4", "F", "4F", "2F"], "correct": 2, "tag": "", "sol": "F ∝ m₁m₂: 2 × 2 = 4."}, {"kind": "mcq", "text": "The gravitational force between two 50 kg students 1.0 m apart is about", "opts": ["1.7 × 10⁻³ N", "3.3 × 10⁻⁹ N", "500 N", "1.7 × 10⁻⁷ N"], "correct": 3, "tag": "", "sol": "6.67 × 10⁻¹¹ × 50 × 50 ÷ 1² ≈ 1.7 × 10⁻⁷ N — far too small to notice.", "tools": ["calc"]}, {"kind": "mcq", "text": "At a height above Earth's surface equal to Earth's radius, g is about", "opts": ["2.5 m/s²", "10 m/s²", "0", "5 m/s²"], "correct": 0, "tag": "", "sol": "Distance from the centre doubles: 10 ÷ 4 = 2.5 m/s²."}, {"kind": "mcq", "text": "A planet has twice Earth's mass and twice Earth's radius. g at its surface is", "opts": ["2.5 m/s²", "20 m/s²", "10 m/s²", "5 m/s²"], "correct": 3, "tag": "", "sol": "g ∝ M ÷ r²: 2 ÷ 4 = ½ of 10."}, {"kind": "mcq", "text": "The gravitational field strength at a point is", "opts": ["the same everywhere in space", "the gravitational force per unit mass on an object there", "the mass per unit volume", "the force per unit distance"], "correct": 1, "tag": "", "sol": "g = F_g ÷ m, measured in N/kg."}, {"kind": "mcq", "text": "Earth pulls the Moon with a force F. The Moon pulls Earth with", "opts": ["zero", "81F", "F ÷ 81", "F"], "correct": 3, "tag": "", "sol": "Gravitational forces come in third-law pairs."}, {"kind": "mcq", "text": "Why can we treat the gravitational force on a ball thrown 20 m high as constant?", "opts": ["the ball's mass is small", "gravity does not depend on distance", "air resistance cancels the change", "20 m is tiny compared with Earth's radius, so g hardly changes"], "correct": 3, "tag": "", "sol": "r changes from 6 400 000 m to 6 400 020 m: negligible."}, {"kind": "blank", "p": "Two lead spheres of 20 kg and 5.0 kg have their centres 0.10 m apart. (G = 6.67 × 10⁻¹¹ N·m²/kg²)", "tag": "", "marks": "", "flat": [{"t": "F_g = __B1__ × 10⁻⁷ N", "a": {"B1": "6.67"}, "expr": "approx"}, {"t": "At 0.20 m apart, F_g = __B1__ × 10⁻⁷ N", "a": {"B1": "1.67"}, "expr": "approx"}, {"t": "The force became __B1__ times smaller.", "a": {"B1": "4"}}], "sol": "6.67 × 10⁻¹¹ × 100 ÷ 0.010 = 6.67 × 10⁻⁷ N.\n÷ 4: ≈ 1.67 × 10⁻⁷ N.\nDoubling r divides F by 2² = 4.", "tools": ["calc"]}, {"kind": "blank", "p": "Mars has 0.11 times Earth's mass and 0.53 times Earth's radius. Take g = 10 m/s² on Earth.", "tag": "", "marks": "", "flat": [{"t": "g on Mars = __B1__ m/s²", "a": {"B1": "3.92"}, "expr": "approx"}, {"t": "A 60 kg rover's mass on Mars = __B1__ kg", "a": {"B1": "60"}}, {"t": "Its weight on Mars = __B1__ N", "a": {"B1": "235"}, "expr": "approx"}], "sol": "10 × 0.11 ÷ 0.53² ≈ 3.92 m/s².\nMass does not change.\n60 × 3.92 ≈ 235 N.", "tools": ["calc"]}, {"kind": "blank", "p": "g = 10 m/s² at Earth's surface (distance R from the centre).", "tag": "", "marks": "", "flat": [{"t": "g at 2R = __B1__ m/s²", "a": {"B1": "2.5"}}, {"t": "g at 3R = __B1__ m/s²", "a": {"B1": "1.11"}, "expr": "approx"}, {"t": "g at 10R = __B1__ m/s²", "a": {"B1": "0.1"}}, {"t": "g at nR = __B1__ (in terms of n)", "a": {"B1": "10/n^2"}, "expr": true}], "sol": "10 ÷ 4 = 2.5.\n10 ÷ 9 ≈ 1.11.\n10 ÷ 100 = 0.1.\ng = 10 ÷ n².", "tools": ["calc"]}]}, {"id": "s10", "label": "2.6.B", "sub": "Apparent weight — LO 2.6.B: describe the conditions under which the magnitude of a system's apparent weight is different from the magnitude of the gravitational force exerted on that system.", "slides": [{"kind": "mcq", "text": "The apparent weight of a person in a lift is", "opts": ["the normal force the floor (or scale) exerts on them", "always equal to mg", "Earth's gravitational force on them", "their mass"], "correct": 0, "tag": "", "sol": "A scale reads the support force."}, {"kind": "mcq", "text": "A 60 kg person is in a lift accelerating upward at 2 m/s². The scale reads", "opts": ["120 N", "600 N", "720 N", "480 N"], "correct": 2, "tag": "", "sol": "F_N = m(g + a) = 60 × 12 = 720 N.", "tools": ["calc"]}, {"kind": "mcq", "text": "A 60 kg person is in a lift accelerating downward at 2 m/s². The scale reads", "opts": ["720 N", "600 N", "0", "480 N"], "correct": 3, "tag": "", "sol": "F_N = 60 × (10 − 2) = 480 N.", "tools": ["calc"]}, {"kind": "mcq", "text": "A 60 kg person is in a lift moving downward at a constant 3 m/s. The scale reads", "opts": ["420 N", "600 N", "780 N", "0"], "correct": 1, "tag": "", "sol": "No acceleration: F_N = mg."}, {"kind": "mcq", "text": "Astronauts on the International Space Station feel weightless because", "opts": ["there is no air in space", "they and the station are falling freely together", "g is zero that far from Earth", "there is no gravity in orbit"], "correct": 1, "tag": "", "sol": "g there is still about 9 N/kg; nothing pushes up on them."}, {"kind": "mcq", "text": "A lift is moving upward but slowing down. A person's scale reading is", "opts": ["less than mg", "zero", "more than mg", "equal to mg"], "correct": 0, "tag": "", "sol": "Slowing while going up: acceleration is downward, so F_N < mg."}, {"kind": "mcq", "text": "If a lift's cable snapped (free fall, no brakes), the scale would read", "opts": ["2mg", "zero", "mg", "mg ÷ 2"], "correct": 1, "tag": "", "sol": "a = g downward: F_N = m(g − g) = 0."}, {"kind": "mcq", "text": "A 50 kg girl's scale in a lift reads 400 N. The lift's acceleration is", "opts": ["2 m/s² upward", "8 m/s² downward", "2 m/s² downward", "zero"], "correct": 2, "tag": "", "sol": "400 − 500 = 50a, a = −2 m/s².", "tools": ["calc"]}, {"kind": "blank", "p": "A 70 kg man stands on a bathroom scale in a lift.", "tag": "", "marks": "", "flat": [{"t": "Reading at rest = __B1__ N", "a": {"B1": "700"}}, {"t": "Reading while accelerating upward at 1.5 m/s² = __B1__ N", "a": {"B1": "805"}}, {"t": "Reading while accelerating downward at 3.0 m/s² = __B1__ N", "a": {"B1": "490"}}, {"t": "Reading in free fall = __B1__ N", "a": {"B1": "0"}}], "sol": "mg = 700 N.\n70 × 11.5 = 805 N.\n70 × 7.0 = 490 N.\nF_N = 0.", "tools": ["calc"]}, {"kind": "blank", "p": "A scale in a lift reads 900 N for an 80 kg person.", "tag": "", "marks": "", "flat": [{"t": "True weight = __B1__ N", "a": {"B1": "800"}}, {"t": "Net force = __B1__ N", "a": {"B1": "100"}}, {"t": "Acceleration = __B1__ m/s²", "a": {"B1": "1.25"}}, {"t": "The acceleration is __B1__ (upward / downward).", "a": {"B1": "upward"}, "expr": "words", "accept": ["up", "upwards"]}, {"t": "The lift is either going up and speeding up, or going down and __B1__ (speeding up / slowing down).", "a": {"B1": "slowing down"}, "expr": "words", "accept": ["slowingdown"]}], "sol": "80 × 10 = 800 N.\n900 − 800 = 100 N (upward).\n100 ÷ 80 = 1.25 m/s².\nF_N > mg.\nUpward acceleration while moving down means slowing.", "tools": ["calc"]}, {"kind": "blank", "p": "A 2.0 kg fish hangs from a spring scale in a lift that accelerates downward at 4.0 m/s².", "tag": "", "marks": "", "flat": [{"t": "Reading = __B1__ N", "a": {"B1": "12"}}, {"t": "Reading when the lift moves at constant speed = __B1__ N", "a": {"B1": "20"}}], "sol": "T = m(g − a) = 2.0 × 6.0 = 12 N.\nNo acceleration: 20 N.", "tools": ["calc"]}]}, {"id": "s11", "label": "2.6.C", "sub": "Inertial and gravitational mass — LO 2.6.C: describe inertial and gravitational mass.", "slides": [{"kind": "mcq", "text": "Inertial mass measures", "opts": ["how strongly it is attracted by gravity", "its weight on Earth", "its volume", "how strongly an object resists changes in its velocity"], "correct": 3, "tag": "", "sol": "m_inertial = F_net ÷ a."}, {"kind": "mcq", "text": "Gravitational mass measures", "opts": ["how strongly an object takes part in gravitational interactions", "its resistance to acceleration", "its speed", "its density"], "correct": 0, "tag": "", "sol": "It appears in F_g = Gm₁m₂ ÷ r²."}, {"kind": "mcq", "text": "Experiments show that inertial mass and gravitational mass are", "opts": ["different by a factor of g", "equivalent (equal)", "equal only on Earth", "unrelated"], "correct": 1, "tag": "", "sol": "Many precise experiments have found no difference."}, {"kind": "mcq", "text": "Because the two masses are equivalent, in a vacuum near Earth", "opts": ["light objects fall faster", "objects fall at constant speed", "all objects fall with the same acceleration", "heavy objects fall faster"], "correct": 2, "tag": "", "sol": "a = F_g ÷ m_inertial = m_grav g ÷ m_inertial = g."}, {"kind": "mcq", "text": "On the ISS an astronaut wants to find her mass. A bathroom scale does not work. She could", "opts": ["use the bathroom scale anyway", "measure her height", "use a pan balance", "push off a spring device with a known force and measure her acceleration"], "correct": 3, "tag": "", "sol": "a = F ÷ m gives inertial mass; weighing needs a support force, which is absent in free fall."}, {"kind": "mcq", "text": "A pan (beam) balance compares", "opts": ["inertial masses", "speeds", "gravitational masses", "volumes"], "correct": 2, "tag": "", "sol": "It balances the gravitational forces on the two pans."}, {"kind": "mcq", "text": "The same 6.0 N force gives cart A an acceleration of 2.0 m/s² and cart B 3.0 m/s². Their inertial masses are", "opts": ["A: 12 kg, B: 18 kg", "A: 3.0 kg, B: 2.0 kg", "both 6.0 kg", "A: 2.0 kg, B: 3.0 kg"], "correct": 1, "tag": "", "sol": "m = F ÷ a.", "tools": ["calc"]}, {"kind": "mcq", "text": "A 5 kg block is taken to the Moon (g = 1.6 m/s²). Which is true (ignore friction)?", "opts": ["its mass is still 5 kg and the same horizontal force gives the same acceleration as on Earth", "its mass becomes 0.8 kg", "it is easier to accelerate horizontally on the Moon", "its inertial mass is smaller on the Moon"], "correct": 0, "tag": "", "sol": "Mass is a property of the object; only its weight changes."}, {"kind": "blank", "p": "A 12 N horizontal force on a frictionless track gives a trolley an acceleration of 1.5 m/s². Its weight is then measured with a spring scale.", "tag": "", "marks": "", "flat": [{"t": "Inertial mass = __B1__ kg", "a": {"B1": "8"}}, {"t": "Predicted spring-scale reading = __B1__ N", "a": {"B1": "80"}}, {"t": "Gravitational mass from that reading = __B1__ kg", "a": {"B1": "8"}}, {"t": "The two masses are __B1__ (equal / different).", "a": {"B1": "equal"}, "expr": "words", "accept": ["same", "thesame"]}], "sol": "12 ÷ 1.5 = 8 kg.\n8 × 10 = 80 N.\n80 ÷ 10 = 8 kg.\nEquivalence of inertial and gravitational mass.", "tools": ["calc"]}, {"kind": "blank", "p": "On the ISS a spring device pushes an astronaut with 150 N and she accelerates at 2.5 m/s².", "tag": "", "marks": "", "flat": [{"t": "Her inertial mass = __B1__ kg", "a": {"B1": "60"}}, {"t": "Her weight on Earth's surface = __B1__ N", "a": {"B1": "600"}}, {"t": "Her inertial mass on the ISS is __B1__ (zero / unchanged / smaller).", "a": {"B1": "unchanged"}, "expr": "words", "accept": ["same", "thesame"]}], "sol": "150 ÷ 2.5 = 60 kg.\n60 × 10 = 600 N.\nMass does not depend on location.", "tools": ["calc"]}, {"kind": "blank", "p": "A 1 kg ball and a 10 kg ball are dropped together (no air resistance).", "tag": "", "marks": "", "flat": [{"t": "F_g on the 1 kg ball = __B1__ N", "a": {"B1": "10"}}, {"t": "F_g on the 10 kg ball = __B1__ N", "a": {"B1": "100"}}, {"t": "Acceleration of the 1 kg ball = __B1__ m/s²", "a": {"B1": "10"}}, {"t": "Acceleration of the 10 kg ball = __B1__ m/s²", "a": {"B1": "10"}}], "sol": "1 × 10 = 10 N.\n10 × 10 = 100 N.\n10 ÷ 1 = 10 m/s².\n100 ÷ 10 = 10 m/s²: ten times the force, ten times the inertia."}]}, {"id": "s12", "label": "2.7.A", "sub": "Kinetic friction — LO 2.7.A: describe kinetic friction between two surfaces.", "slides": [{"kind": "mcq", "text": "Kinetic friction on a sliding object points", "opts": ["opposite to its motion relative to the surface", "perpendicular to the surface", "straight down", "in the direction of its motion"], "correct": 0, "tag": "", "sol": "It opposes the relative sliding."}, {"kind": "mcq", "text": "A 10 kg box slides across a level floor with μ_k = 0.30. The friction force is", "opts": ["0.30 N", "100 N", "30 N", "3 N"], "correct": 2, "tag": "", "sol": "μ_k F_N = 0.30 × 100 = 30 N.", "tools": ["calc"]}, {"kind": "mcq", "text": "The coefficient of kinetic friction depends mainly on", "opts": ["the sliding speed", "the contact area", "the mass of the object", "the materials of the two surfaces"], "correct": 3, "tag": "", "sol": "In this model μ is a property of the pair of surfaces."}, {"kind": "mcq", "text": "Doubling the mass of a box sliding on a level floor doubles", "opts": ["μ_k", "the kinetic friction force", "nothing", "the deceleration caused by friction"], "correct": 1, "tag": "", "sol": "F_N doubles, so F_f doubles; a = μ_k g is unchanged."}, {"kind": "mcq", "text": "A box slides on a level floor with only friction acting horizontally; μ_k = 0.25. Its deceleration is", "opts": ["25 m/s²", "2.5 m/s²", "10 m/s²", "0.25 m/s²"], "correct": 1, "tag": "", "sol": "a = μ_k g = 2.5 m/s².", "tools": ["calc"]}, {"kind": "mcq", "text": "While a box slides, you press down on its top. The kinetic friction", "opts": ["decreases", "stays the same", "becomes zero", "increases"], "correct": 3, "tag": "", "sol": "F_N increases, so μ_k F_N increases."}, {"kind": "mcq", "text": "A brick slides on its large face, then on its small face (same materials). The kinetic friction", "opts": ["doubles", "halves", "depends on speed", "stays the same"], "correct": 3, "tag": "", "sol": "Friction does not depend on contact area in this model."}, {"kind": "mcq", "text": "A 200 N crate is pulled at constant velocity by a horizontal 60 N force. μ_k is", "opts": ["0.60", "0.30", "60", "3.3"], "correct": 1, "tag": "", "sol": "Friction = 60 N; 60 ÷ 200 = 0.30.", "tools": ["calc"]}, {"kind": "blank", "p": "A 4.0 kg block slides on a level floor with initial speed 6.0 m/s; μ_k = 0.20.", "tag": "", "marks": "", "flat": [{"t": "Normal force = __B1__ N", "a": {"B1": "40"}}, {"t": "Friction force = __B1__ N", "a": {"B1": "8"}}, {"t": "Deceleration = __B1__ m/s²", "a": {"B1": "2"}}, {"t": "Stopping distance = __B1__ m", "a": {"B1": "9"}}], "sol": "4.0 × 10 = 40 N.\n0.20 × 40 = 8 N.\n8 ÷ 4.0 = 2 m/s².\n36 ÷ (2 × 2) = 9 m.", "tools": ["calc"]}, {"kind": "blank", "p": "A 30 kg crate is pulled with a horizontal force of 150 N; μ_k = 0.40.", "tag": "", "marks": "", "flat": [{"t": "Normal force = __B1__ N", "a": {"B1": "300"}}, {"t": "Friction = __B1__ N", "a": {"B1": "120"}}, {"t": "Net force = __B1__ N", "a": {"B1": "30"}}, {"t": "Acceleration = __B1__ m/s²", "a": {"B1": "1"}}], "sol": "30 × 10 = 300 N.\n0.40 × 300 = 120 N.\n150 − 120 = 30 N.\n30 ÷ 30 = 1 m/s².", "tools": ["calc"]}, {"kind": "blank", "p": "A 50 kg crate is pulled by a rope at 30° above the horizontal with a tension of 200 N; μ_k = 0.30.", "tag": "", "marks": "", "flat": [{"t": "Vertical component of tension = __B1__ N", "a": {"B1": "100"}}, {"t": "Normal force = __B1__ N", "a": {"B1": "400"}}, {"t": "Friction = __B1__ N", "a": {"B1": "120"}}, {"t": "Acceleration = __B1__ m/s²", "a": {"B1": "1.06"}, "expr": "approx"}], "sol": "200 sin 30° = 100 N.\n500 − 100 = 400 N.\n0.30 × 400 = 120 N.\n(173.2 − 120) ÷ 50 ≈ 1.06 m/s².", "tools": ["calc"]}, {"kind": "blank", "p": "A 2.0 kg block slides down a 30° ramp with μ_k = 0.20.", "tag": "", "marks": "", "flat": [{"t": "Component of F_g down the ramp = __B1__ N", "a": {"B1": "10"}}, {"t": "Normal force = __B1__ N", "a": {"B1": "17.3"}, "expr": "approx"}, {"t": "Friction = __B1__ N", "a": {"B1": "3.46"}, "expr": "approx"}, {"t": "Acceleration = __B1__ m/s²", "a": {"B1": "3.27"}, "expr": "approx"}], "sol": "20 sin 30° = 10 N.\n20 cos 30° ≈ 17.3 N.\n0.20 × 17.3 ≈ 3.46 N.\n(10 − 3.46) ÷ 2.0 ≈ 3.27 m/s².", "fig": "<svg class=\"figsvg\" viewBox=\"0 0 280 170\" role=\"img\"><defs><marker id=\"ah\" viewBox=\"0 0 10 10\" refX=\"9\" refY=\"5\" markerWidth=\"7\" markerHeight=\"7\" orient=\"auto\"><path d=\"M0,1 L10,5 L0,9 z\" class=\"ahd\"/></marker><marker id=\"ahs\" viewBox=\"0 0 10 10\" refX=\"1\" refY=\"5\" markerWidth=\"7\" markerHeight=\"7\" orient=\"auto\"><path d=\"M10,1 L0,5 L10,9 z\" class=\"ahd\"/></marker></defs><path d=\"M20,156 L260.0,156 L260.0,17.4 Z\" style=\"fill:var(--paper-2);stroke:var(--ink);stroke-width:1.5\"/><path class=\"wg\" d=\"M20.0,156.0 L50.0,156.0 A30,30 0 0 0 46.0,141.0 Z\"/><text class=\"al\" x=\"62.5\" y=\"144.6\" text-anchor=\"middle\" dominant-baseline=\"middle\">30°</text><path class=\"ra\" d=\"M260.0,147.0 L251.0,147.0 L251.0,156.0\"/><g transform=\"translate(152.0,79.8) rotate(-30)\"><rect x=\"-17\" y=\"-30\" width=\"34\" height=\"30\" style=\"fill:var(--gold-soft);stroke:var(--ink);stroke-width:1.3\"/><text class=\"lb\" x=\"0\" y=\"-15\" text-anchor=\"middle\" dominant-baseline=\"middle\">2.0 kg</text></g></svg>", "tools": ["calc"]}]}, {"id": "s13", "label": "2.7.B", "sub": "Static friction — LO 2.7.B: describe static friction between two surfaces.", "slides": [{"kind": "mcq", "text": "A box rests on a level floor with nothing pushing it sideways. The static friction on it is", "opts": ["zero", "mg", "μ_k mg", "μ_s mg"], "correct": 0, "tag": "", "sol": "No attempted sliding, so no friction is needed."}, {"kind": "mcq", "text": "A 100 N box (μ_s = 0.50) is pushed horizontally with 20 N and does not move. The static friction is", "opts": ["100 N", "50 N", "20 N", "0"], "correct": 2, "tag": "", "sol": "Static friction matches the push, up to its maximum."}, {"kind": "mcq", "text": "A 100 N box on a level floor has μ_s = 0.50. The smallest horizontal push that starts it sliding is just over", "opts": ["50 N", "100 N", "20 N", "200 N"], "correct": 0, "tag": "", "sol": "Maximum static friction = 0.50 × 100 = 50 N."}, {"kind": "mcq", "text": "For most pairs of surfaces", "opts": ["μ_s > μ_k, so starting to slide is harder than keeping sliding", "μ_s depends on speed", "μ_s = μ_k", "μ_s < μ_k"], "correct": 0, "tag": "", "sol": "Friction drops once sliding starts."}, {"kind": "mcq", "text": "A car accelerates forward from rest without skidding. The friction from the road on its driven tyres points", "opts": ["backward (static friction)", "forward (static friction)", "upward", "backward (kinetic friction)"], "correct": 1, "tag": "", "sol": "The tyre pushes the road back; the road pushes the tyre forward."}, {"kind": "mcq", "text": "A book rests on a tilted board without slipping. The static friction on it points", "opts": ["into the board", "up the slope", "down the slope", "vertically up"], "correct": 1, "tag": "", "sol": "It opposes the tendency to slide down."}, {"kind": "mcq", "text": "A 20 kg box on a truck bed does not slip while the truck accelerates at 2 m/s². The friction on the box is", "opts": ["200 N forward", "zero", "40 N forward", "40 N backward"], "correct": 2, "tag": "", "sol": "Friction is the only horizontal force on the box: 20 × 2 = 40 N forward.", "tools": ["calc"]}, {"kind": "mcq", "text": "A 20 kg box sits on a truck bed with μ_s = 0.40. The largest acceleration the truck can have without the box slipping is", "opts": ["4 m/s²", "2 m/s²", "0.4 m/s²", "40 m/s²"], "correct": 0, "tag": "", "sol": "μ_s mg = ma, a = μ_s g = 4 m/s².", "tools": ["calc"]}, {"kind": "blank", "p": "A 5.0 kg block on a level floor has μ_s = 0.60 and μ_k = 0.40. A horizontal push is slowly increased from zero.", "tag": "", "marks": "", "flat": [{"t": "Normal force = __B1__ N", "a": {"B1": "50"}}, {"t": "Maximum static friction = __B1__ N", "a": {"B1": "30"}}, {"t": "Friction when the push is 18 N = __B1__ N", "a": {"B1": "18"}}, {"t": "It starts to slide when the push exceeds __B1__ N", "a": {"B1": "30"}}, {"t": "Friction once it is sliding = __B1__ N", "a": {"B1": "20"}}], "sol": "5.0 × 10 = 50 N.\n0.60 × 50 = 30 N.\nStatic friction matches the push.\nAt the maximum static friction.\n0.40 × 50 = 20 N.", "tools": ["calc"]}, {"kind": "blank", "p": "A coin on a book starts to slide when the book is tilted to 30°.", "tag": "", "marks": "", "flat": [{"t": "μ_s = __B1__", "a": {"B1": "0.577"}, "expr": "approx"}, {"t": "For μ_s = 1.0 the coin would first slide at __B1__°", "a": {"B1": "45"}}, {"t": "A heavier coin of the same metal starts to slide at __B1__ angle (a smaller / the same / a larger).", "a": {"B1": "the same"}, "expr": "words", "accept": ["same", "thesame"]}], "sol": "μ_s = tan 30° ≈ 0.577.\ntan θ = 1, θ = 45°.\nMass cancels: mg sin θ = μ_s mg cos θ.", "tools": ["calc"]}, {"kind": "blank", "p": "A 40 kg crate stands on a truck bed with μ_s = 0.30.", "tag": "", "marks": "", "flat": [{"t": "Maximum static friction = __B1__ N", "a": {"B1": "120"}}, {"t": "Largest acceleration without slipping = __B1__ m/s²", "a": {"B1": "3"}}, {"t": "If the truck accelerates at 4 m/s², the crate __B1__ (slides / stays).", "a": {"B1": "slides"}, "expr": "words", "accept": ["slide", "slips"]}], "sol": "0.30 × 400 = 120 N.\n120 ÷ 40 = 3 m/s².\nIt would need 160 N > 120 N.", "tools": ["calc"]}]}, {"id": "s14", "label": "2.8.A", "sub": "Spring forces — LO 2.8.A: describe the force exerted on an object by an ideal spring.", "slides": [{"kind": "mcq", "text": "In Hooke's law F_s = −kΔx, the minus sign means", "opts": ["the force always points left", "the spring loses energy", "k is negative", "the spring force is opposite to the displacement from its natural length"], "correct": 3, "tag": "", "sol": "It is a restoring force."}, {"kind": "mcq", "text": "A spring with k = 200 N/m is stretched by 0.05 m. The spring force has magnitude", "opts": ["0.00025 N", "4000 N", "10 N", "40 N"], "correct": 2, "tag": "", "sol": "200 × 0.05 = 10 N.", "tools": ["calc"]}, {"kind": "mcq", "text": "A spring stretches 4 cm under a 2 N load. Under 5 N it stretches", "opts": ["20 cm", "8 cm", "2.5 cm", "10 cm"], "correct": 3, "tag": "", "sol": "Extension ∝ force: 4 × 5 ÷ 2 = 10 cm."}, {"kind": "mcq", "text": "The SI unit of spring constant k is", "opts": ["N", "N·m", "m/N", "N/m"], "correct": 3, "tag": "", "sol": "k = F ÷ Δx."}, {"kind": "mcq", "text": "A 0.50 kg mass hangs at rest from a spring with k = 100 N/m. The extension is", "opts": ["0.05 m", "0.5 m", "50 m", "5 m"], "correct": 0, "tag": "", "sol": "kΔx = mg: Δx = 5 ÷ 100 = 0.05 m.", "tools": ["calc"]}, {"kind": "mcq", "text": "Compared with a soft spring, a stiffer spring has", "opts": ["a larger k and stretches less for the same force", "a smaller k", "a larger k and stretches more", "the same k"], "correct": 0, "tag": "", "sol": "Δx = F ÷ k."}, {"kind": "mcq", "text": "An ideal spring", "opts": ["is always stretched", "has negligible mass and obeys Hooke's law", "is very heavy", "exerts a constant force"], "correct": 1, "tag": "", "sol": "That is the model used in AP Physics 1."}, {"kind": "mcq", "text": "Two identical springs (k each) hang side by side and share a load. The pair acts like one spring of constant", "opts": ["k²", "k ÷ 2", "k", "2k"], "correct": 3, "tag": "", "sol": "Parallel springs: k_eq = k + k."}, {"kind": "blank", "p": "Masses are hung from a spring and the extension measured:\nm (kg): 0.10, 0.20, 0.30, 0.40   →   Δx (cm): 2.5, 5.0, 7.5, 10.0", "tag": "", "marks": "", "flat": [{"t": "Force for the 0.30 kg mass = __B1__ N", "a": {"B1": "3"}}, {"t": "k = __B1__ N/m", "a": {"B1": "40"}}, {"t": "Predicted extension for 0.50 kg = __B1__ cm", "a": {"B1": "12.5"}}], "sol": "0.30 × 10 = 3 N.\n3 ÷ 0.075 = 40 N/m (same for every row).\n5 ÷ 40 = 0.125 m.", "tools": ["calc", "desmos"], "desmos": [{"type": "table", "columns": [{"latex": "x_1", "values": ["0.025", "0.05", "0.075", "0.1"]}, {"latex": "y_1", "values": ["1", "2", "3", "4"]}]}, "y_1\\sim kx_1"]}, {"kind": "blank", "p": "A spring (k = 250 N/m) fixed to a wall on the left is pushed in (compressed) by 0.08 m by a toy on its right. Take right as positive.", "tag": "", "marks": "", "flat": [{"t": "Δx = __B1__ m", "a": {"B1": "-0.08"}}, {"t": "Magnitude of the spring force = __B1__ N", "a": {"B1": "20"}}, {"t": "The spring force on the toy points __B1__ (left / right).", "a": {"B1": "right"}, "expr": "words"}], "sol": "Compressed: the end moved left, Δx = −0.08 m.\n250 × 0.08 = 20 N.\nF = −kΔx is positive: to the right, back towards natural length.", "fig": "<svg class=\"figsvg\" viewBox=\"0 0 300 110\" role=\"img\"><defs><marker id=\"ah\" viewBox=\"0 0 10 10\" refX=\"9\" refY=\"5\" markerWidth=\"7\" markerHeight=\"7\" orient=\"auto\"><path d=\"M0,1 L10,5 L0,9 z\" class=\"ahd\"/></marker><marker id=\"ahs\" viewBox=\"0 0 10 10\" refX=\"1\" refY=\"5\" markerWidth=\"7\" markerHeight=\"7\" orient=\"auto\"><path d=\"M10,1 L0,5 L10,9 z\" class=\"ahd\"/></marker></defs><line x1=\"14\" y1=\"20\" x2=\"14\" y2=\"86\" style=\"stroke:var(--ink);stroke-width:3\"/><line x1=\"10\" y1=\"86\" x2=\"290\" y2=\"86\" style=\"stroke:var(--ink);stroke-width:1.5\"/><polyline points=\"14,60 40,50 52,70 64,50 76,70 88,50 100,70 112,50 124,70 136,50 148,70 160,50 172,70 190,60\" style=\"fill:none;stroke:var(--accent-text);stroke-width:2\"/><rect x=\"190\" y=\"36\" width=\"50\" height=\"50\" style=\"fill:var(--gold-soft);stroke:var(--ink);stroke-width:1.3\"/><text class=\"lb\" x=\"215.0\" y=\"61.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">toy</text><text class=\"lb\" x=\"110.0\" y=\"36.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">k = 250 N/m</text></svg>", "tools": ["calc"]}, {"kind": "blank", "p": "A 2.0 kg block hangs at rest from a spring with k = 400 N/m.", "tag": "", "marks": "", "flat": [{"t": "Extension = __B1__ m", "a": {"B1": "0.05"}}, {"t": "The block is pulled down a further 0.03 m. Spring force = __B1__ N", "a": {"B1": "32"}}, {"t": "Net force just after release = __B1__ N (upward)", "a": {"B1": "12"}}, {"t": "Acceleration just after release = __B1__ m/s²", "a": {"B1": "6"}}], "sol": "20 ÷ 400 = 0.05 m.\n400 × 0.08 = 32 N.\n32 − 20 = 12 N.\n12 ÷ 2.0 = 6 m/s² upward.", "tools": ["calc"]}, {"kind": "blank", "p": "Two springs, 150 N/m and 250 N/m, hang side by side and together hold a 40 N load.", "tag": "", "marks": "", "flat": [{"t": "Equivalent spring constant = __B1__ N/m", "a": {"B1": "400"}}, {"t": "Extension = __B1__ m", "a": {"B1": "0.1"}}, {"t": "Force from the 250 N/m spring = __B1__ N", "a": {"B1": "25"}}], "sol": "Parallel: 150 + 250 = 400 N/m.\n40 ÷ 400 = 0.10 m.\n250 × 0.10 = 25 N.", "tools": ["calc"]}]}, {"id": "s15", "label": "2.9.A", "sub": "Circular motion — LO 2.9.A: describe the motion of an object traveling in a circular path.", "slides": [{"kind": "mcq", "text": "For an object in uniform circular motion, the acceleration points", "opts": ["away from the centre", "nowhere: it is zero", "along the velocity", "toward the centre of the circle"], "correct": 3, "tag": "", "sol": "Centripetal: the velocity changes direction toward the centre."}, {"kind": "mcq", "text": "An object moves at 6 m/s in a circle of radius 3 m. Its centripetal acceleration is", "opts": ["12 m/s²", "18 m/s²", "36 m/s²", "2 m/s²"], "correct": 0, "tag": "", "sol": "v² ÷ r = 36 ÷ 3 = 12 m/s².", "tools": ["calc"]}, {"kind": "mcq", "text": "The speed is doubled on the same circle. The centripetal acceleration becomes", "opts": ["the same", "4 times as large", "half as large", "2 times as large"], "correct": 1, "tag": "", "sol": "a_c ∝ v²."}, {"kind": "mcq", "text": "A stone whirled on a string in a horizontal circle is released when the string breaks. It moves", "opts": ["along the tangent at the point of release", "straight outward along the radius", "toward the centre", "in a spiral"], "correct": 0, "tag": "", "sol": "With no centripetal force it continues with its velocity (first law).", "fig": "<svg class=\"figsvg\" viewBox=\"0 0 230 200\" role=\"img\"><defs><marker id=\"ah\" viewBox=\"0 0 10 10\" refX=\"9\" refY=\"5\" markerWidth=\"7\" markerHeight=\"7\" orient=\"auto\"><path d=\"M0,1 L10,5 L0,9 z\" class=\"ahd\"/></marker><marker id=\"ahs\" viewBox=\"0 0 10 10\" refX=\"1\" refY=\"5\" markerWidth=\"7\" markerHeight=\"7\" orient=\"auto\"><path d=\"M10,1 L0,5 L10,9 z\" class=\"ahd\"/></marker></defs><circle cx=\"115.0\" cy=\"106.0\" r=\"70\" style=\"fill:none;stroke:var(--ink);stroke-width:1.3;stroke-dasharray:5 4\"/><line class=\"ln\" x1=\"115.0\" y1=\"106.0\" x2=\"175.6\" y2=\"71.0\"/><text class=\"lb\" x=\"137.5\" y=\"79.2\" text-anchor=\"middle\" dominant-baseline=\"middle\">r</text><line style=\"stroke:var(--danger);stroke-width:2.2\" x1=\"175.6\" y1=\"71.0\" x2=\"146.6\" y2=\"20.8\" marker-end=\"url(#ah)\"/><text class=\"lb\" x=\"139.6\" y=\"8.6\" text-anchor=\"middle\" dominant-baseline=\"middle\">v</text><circle cx=\"175.6\" cy=\"71.0\" r=\"7\" style=\"fill:var(--accent-text)\"/><circle cx=\"115.0\" cy=\"106.0\" r=\"3\" style=\"fill:var(--ink)\"/></svg>"}, {"kind": "mcq", "text": "A car rounds a flat bend at constant speed. The force toward the centre is provided by", "opts": ["a centrifugal force", "the engine", "the normal force", "static friction from the road on the tyres"], "correct": 3, "tag": "", "sol": "Friction on a flat road supplies ΣF_c."}, {"kind": "mcq", "text": "A 1200 kg car rounds a bend of radius 50 m at 20 m/s. The net force on it is", "opts": ["480 N toward the centre", "9600 N outward", "zero", "9600 N toward the centre"], "correct": 3, "tag": "", "sol": "1200 × 400 ÷ 50 = 9600 N.", "tools": ["calc"]}, {"kind": "mcq", "text": "A bucket of water swings in a vertical circle of radius 0.90 m. The smallest speed at the top that keeps the water in is", "opts": ["1.5 m/s", "3 m/s", "9 m/s", "0.9 m/s"], "correct": 1, "tag": "", "sol": "mg = mv² ÷ r: v = √(gr) = √9 = 3 m/s.", "tools": ["calc"]}, {"kind": "mcq", "text": "An object moves round a circle and is speeding up. Its acceleration", "opts": ["has a component toward the centre and a component along the velocity", "is zero", "points exactly along the velocity", "points exactly toward the centre"], "correct": 0, "tag": "", "sol": "Centripetal part changes direction; tangential part changes speed."}, {"kind": "blank", "p": "A 0.20 kg stone on a 0.50 m string is whirled in a horizontal circle at 2.0 revolutions per second (ignore gravity's effect on the string).", "tag": "", "marks": "", "flat": [{"t": "Period = __B1__ s", "a": {"B1": "0.5"}}, {"t": "Speed = __B1__ m/s", "a": {"B1": "6.28"}, "expr": "approx"}, {"t": "Centripetal acceleration = __B1__ m/s²", "a": {"B1": "79"}, "expr": "approx"}, {"t": "Tension = __B1__ N", "a": {"B1": "15.8"}, "expr": "approx"}], "sol": "1 ÷ 2.0 = 0.50 s.\n2π × 0.50 ÷ 0.50 ≈ 6.28 m/s.\n6.28² ÷ 0.50 ≈ 79.0 m/s².\n0.20 × 79.0 ≈ 15.8 N.", "tools": ["calc"]}, {"kind": "blank", "p": "A 1000 kg car drives over the top of a hump-backed bridge of radius 40 m at 10 m/s.", "tag": "", "marks": "", "flat": [{"t": "Centripetal acceleration = __B1__ m/s²", "a": {"B1": "2.5"}}, {"t": "Normal force at the top = __B1__ N", "a": {"B1": "7500"}}, {"t": "Speed at which the car just loses contact = __B1__ m/s", "a": {"B1": "20"}}], "sol": "100 ÷ 40 = 2.5 m/s² (downward).\nmg − F_N = ma: F_N = 1000(10 − 2.5) = 7500 N.\nF_N = 0: v² = gr = 400, v = 20 m/s.", "tools": ["calc"]}, {"kind": "blank", "p": "A 0.50 kg ball on a string moves in a vertical circle of radius 0.80 m.", "tag": "", "marks": "", "flat": [{"t": "At the top, speed 4.0 m/s: tension = __B1__ N", "a": {"B1": "5"}}, {"t": "At the bottom, speed 6.0 m/s: tension = __B1__ N", "a": {"B1": "27.5"}}, {"t": "Smallest possible speed at the top = __B1__ m/s", "a": {"B1": "2.83"}, "expr": "approx"}], "sol": "T + 5 = 0.50 × 16 ÷ 0.80 = 10, T = 5 N.\nT − 5 = 0.50 × 36 ÷ 0.80 = 22.5, T = 27.5 N.\nT = 0: v = √(gr) = √8 ≈ 2.83 m/s.", "tools": ["calc"]}, {"kind": "blank", "p": "A car takes a flat bend of radius 45 m; μ_s between tyres and road = 0.50.", "tag": "", "marks": "", "flat": [{"t": "Largest centripetal acceleration friction can give = __B1__ m/s²", "a": {"B1": "5"}}, {"t": "Maximum speed = __B1__ m/s", "a": {"B1": "15"}}, {"t": "Does the maximum speed depend on the car's mass? __B1__ (yes / no)", "a": {"B1": "no"}, "expr": "words"}], "sol": "μ_s g = 5 m/s².\nv² = 5 × 45 = 225, v = 15 m/s.\nm cancels: μ_s mg = mv² ÷ r.", "tools": ["calc"]}]}, {"id": "s16", "label": "2.9.B", "sub": "Circular orbits — LO 2.9.B: describe circular orbits using Kepler's third law.", "slides": [{"kind": "mcq", "text": "For a satellite in a circular orbit, the force toward the centre of the orbit is", "opts": ["a rocket thrust", "the gravitational force from the planet", "zero, since it is weightless", "a centrifugal force"], "correct": 1, "tag": "", "sol": "Gravity alone provides the centripetal force."}, {"kind": "mcq", "text": "Kepler's third law for circular orbits around the same body states that T² is proportional to", "opts": ["1 ÷ R²", "R³", "R", "R²"], "correct": 1, "tag": "", "sol": "T² = (4π² ÷ GM)R³."}, {"kind": "mcq", "text": "A satellite moves to an orbit of 4 times the radius. Its period is multiplied by", "opts": ["8", "4", "16", "2"], "correct": 0, "tag": "", "sol": "T ∝ R^(3/2): 4¹.5 = 8.", "tools": ["calc"]}, {"kind": "mcq", "text": "Orbital speed is v = √(GM ÷ R). A satellite in a larger orbit has", "opts": ["a larger speed and a longer period", "a larger speed and a shorter period", "a smaller speed and a longer period", "the same speed"], "correct": 2, "tag": "", "sol": "v falls as R grows; T grows as R^(3/2)."}, {"kind": "mcq", "text": "The period of a satellite in a circular orbit does NOT depend on", "opts": ["the orbit radius", "the planet's mass", "G", "the satellite's mass"], "correct": 3, "tag": "", "sol": "m cancels from GMm ÷ R² = mv² ÷ R."}, {"kind": "mcq", "text": "Satellites of 500 kg and 1000 kg share the same circular orbit. Their speeds are", "opts": ["larger for the 1000 kg one", "larger for the 500 kg one", "equal", "in the ratio 1 : 2"], "correct": 2, "tag": "", "sol": "v = √(GM ÷ R) does not contain the satellite's mass."}, {"kind": "mcq", "text": "Earth orbits the Sun at 1 AU with a period of 1 year. A planet orbiting at 9 AU has a period of", "opts": ["81 years", "27 years", "9 years", "3 years"], "correct": 1, "tag": "", "sol": "T = 9¹.5 = 27 years.", "tools": ["calc"]}, {"kind": "mcq", "text": "A geostationary communications satellite stays above one point on the equator. Its period is", "opts": ["one month", "12 hours", "90 minutes", "24 hours"], "correct": 3, "tag": "", "sol": "It turns with Earth."}, {"kind": "blank", "p": "A satellite orbits Earth at R = 8.0 × 10⁶ m from Earth's centre. Take GM = 4.0 × 10¹⁴ m³/s² for Earth.", "tag": "", "marks": "", "flat": [{"t": "g at the orbit = __B1__ m/s²", "a": {"B1": "6.25"}}, {"t": "Orbital speed = __B1__ m/s", "a": {"B1": "7071"}, "expr": "approx"}, {"t": "Period = __B1__ s", "a": {"B1": "7109"}, "expr": "approx"}, {"t": "Its acceleration is __B1__ than g at Earth's surface (greater / less).", "a": {"B1": "less"}, "expr": "words"}], "sol": "GM ÷ R² = 4.0 × 10¹⁴ ÷ 6.4 × 10¹³ = 6.25 m/s².\n√(GM ÷ R) = √(5.0 × 10⁷) ≈ 7070 m/s.\n2πR ÷ v ≈ 7110 s (about 2 h).\n6.25 < 10.", "tools": ["calc"]}, {"kind": "blank", "p": "Three of Jupiter's moons:\nT (days): 1.77, 3.55, 7.15   →   R (10⁸ m): 4.22, 6.71, 10.7", "tag": "", "marks": "", "flat": [{"t": "T² ÷ R³ for the first moon (these units) = __B1__", "a": {"B1": "0.0417"}, "expr": "approx"}, {"t": "For all three moons T² ÷ R³ is __B1__ (the same / different).", "a": {"B1": "the same"}, "expr": "words", "accept": ["same", "thesame", "constant"]}, {"t": "A fourth moon orbits at R = 18.8 × 10⁸ m. Predicted T = __B1__ days", "a": {"B1": "16.6"}, "expr": "approx"}], "sol": "1.77² ÷ 4.22³ ≈ 0.0417.\n3.55² ÷ 6.71³ ≈ 0.0417; 7.15² ÷ 10.7³ ≈ 0.0417.\nT = √(0.0417 × 18.8³) ≈ 16.6 days.", "tools": ["calc", "desmos"], "desmos": [{"type": "table", "columns": [{"latex": "x_1", "values": ["4.22", "6.71", "10.7"]}, {"latex": "y_1", "values": ["1.77", "3.55", "7.15"]}]}, "y_1\\sim ax_1^{1.5}"]}, {"kind": "blank", "p": "Derive the orbital speed. A satellite of mass m orbits a planet of mass M at radius R.", "tag": "", "marks": "", "flat": [{"t": "From GMm ÷ R² = mv² ÷ R: v² = __B1__ (in terms of G, M, R)", "a": {"B1": "G*M/R"}, "expr": true}, {"t": "Does v depend on m? __B1__ (yes / no)", "a": {"B1": "no"}, "expr": "words"}, {"t": "If R is made 4 times larger, v is multiplied by __B1__", "a": {"B1": "0.5"}}], "sol": "Cancel m and one R: v² = GM ÷ R.\nm cancels.\nv ∝ 1 ÷ √R: 1 ÷ √4 = 0.5."}]}, {"id": "s17", "label": "Test A", "sub": "Test A — Knowing and understanding", "slides": [{"kind": "mcq", "text": "A lorry moves along a straight road at a constant 15 m/s. The net force on it is", "opts": ["in the direction of motion", "opposite to the motion", "zero", "equal to its weight"], "correct": 2, "tag": "", "sol": "Constant velocity ⇒ ΣF = 0. [2.4.A]"}, {"kind": "mcq", "text": "A net force of 15 N acts on a 5 kg trolley. Its acceleration is", "opts": ["75 m/s²", "3 m/s²", "0.33 m/s²", "10 m/s²"], "correct": 1, "tag": "", "sol": "15 ÷ 5 = 3 m/s². [2.5.A]", "tools": ["calc"]}, {"kind": "mcq", "text": "A small car and a bus collide. Compared with the force the bus exerts on the car, the force the car exerts on the bus is", "opts": ["zero", "larger", "equal in size", "smaller"], "correct": 2, "tag": "", "sol": "Newton's third law. [2.3.A]"}, {"kind": "mcq", "text": "The distance between two asteroids is tripled. The gravitational force between them becomes", "opts": ["3F", "F ÷ 3", "9F", "F ÷ 9"], "correct": 3, "tag": "", "sol": "Inverse square: 1 ÷ 3². [2.6.A]"}, {"kind": "mcq", "text": "A 20 kg box slides across a floor with μ_k = 0.25. The friction force is", "opts": ["200 N", "5 N", "80 N", "50 N"], "correct": 3, "tag": "", "sol": "0.25 × 200 = 50 N. [2.7.A]", "tools": ["calc"]}, {"kind": "mcq", "text": "A 30 N force stretches a spring by 0.15 m. Its spring constant is", "opts": ["45 N/m", "4.5 N/m", "200 N/m", "0.005 N/m"], "correct": 2, "tag": "", "sol": "30 ÷ 0.15 = 200 N/m. [2.8.A]", "tools": ["calc"]}, {"kind": "mcq", "text": "A cyclist rides round a circular track of radius 20 m at 10 m/s. Her centripetal acceleration is", "opts": ["0.5 m/s²", "200 m/s²", "2 m/s²", "5 m/s²"], "correct": 3, "tag": "", "sol": "100 ÷ 20 = 5 m/s². [2.9.A]", "tools": ["calc"]}, {"kind": "mcq", "text": "Inertial mass and gravitational mass are", "opts": ["equal only on Earth", "unrelated", "experimentally equivalent", "different by a factor of g"], "correct": 2, "tag": "", "sol": "Every precise experiment finds them equal, so all objects fall with the same g. [2.6.C]"}, {"kind": "blank", "p": "A 3 kg mass is at x = 0 and a 1 kg mass is at x = 2.0 m on a light rod.", "tag": "", "marks": "", "flat": [{"t": "x_cm = __B1__ m", "a": {"B1": "0.5"}}, {"t": "The centre of mass is nearer the __B1__ kg mass (3 / 1).", "a": {"B1": "3"}, "expr": "words", "accept": ["three"]}], "sol": "(0 + 2) ÷ 4 = 0.5 m. [2.1.B]\nThe more massive part.", "tools": ["calc"]}, {"kind": "blank", "p": "A 50 kg student stands on a scale in a lift that accelerates upward at 1.0 m/s².", "tag": "", "marks": "", "flat": [{"t": "Scale reading = __B1__ N", "a": {"B1": "550"}}, {"t": "Gravitational force on her = __B1__ N", "a": {"B1": "500"}}], "sol": "50 × 11 = 550 N. [2.6.B]\nmg = 500 N.", "tools": ["calc"]}]}, {"id": "s18", "label": "Test B", "sub": "Test B — Investigating patterns", "slides": [{"kind": "blank", "p": "A trolley is pulled with different net forces:\nF (N): 1, 2, 3, 4   →   a (m/s²): 0.5, 1.0, 1.5, 2.0", "tag": "", "marks": "", "flat": [{"t": "Slope of a against F = __B1__ kg⁻¹", "a": {"B1": "0.5"}}, {"t": "Mass of the trolley = __B1__ kg", "a": {"B1": "2"}}, {"t": "Predicted a for F = 7 N = __B1__ m/s²", "a": {"B1": "3.5"}}], "sol": "0.5 per newton.\nSlope = 1 ÷ m, m = 2 kg.\n7 ÷ 2 = 3.5 m/s².", "tools": ["calc", "desmos"], "desmos": [{"type": "table", "columns": [{"latex": "x_1", "values": ["1", "2", "3", "4"]}, {"latex": "y_1", "values": ["0.5", "1", "1.5", "2"]}]}, "y_1\\sim bx_1"]}, {"kind": "blank", "p": "The same net force acts on carts of different mass:\nm (kg): 1, 2, 4, 5   →   a (m/s²): 12, 6, 3, 2.4", "tag": "", "marks": "", "flat": [{"t": "m × a for every row = __B1__ N", "a": {"B1": "12"}}, {"t": "So a = __B1__ (in terms of m)", "a": {"B1": "12/m"}, "expr": true}, {"t": "Predicted a for m = 8 kg = __B1__ m/s²", "a": {"B1": "1.5"}}], "sol": "12, 12, 12, 12.\na = 12 ÷ m: inverse proportion.\n12 ÷ 8 = 1.5 m/s².", "tools": ["calc", "desmos"], "desmos": [{"type": "table", "columns": [{"latex": "x_1", "values": ["1", "2", "4", "5"]}, {"latex": "y_1", "values": ["12", "6", "3", "2.4"]}]}, "y_1\\sim c/x_1"]}, {"kind": "blank", "p": "A block is dragged at constant speed with different loads on top:\nF_N (N): 10, 20, 30, 40   →   F_f (N): 3.5, 7.0, 10.5, 14.0", "tag": "", "marks": "", "flat": [{"t": "μ_k = __B1__", "a": {"B1": "0.35"}}, {"t": "Predicted friction for F_N = 55 N = __B1__ N", "a": {"B1": "19.25"}}, {"t": "Friction is __B1__ to the normal force (proportional / inversely proportional).", "a": {"B1": "proportional"}, "expr": "words", "accept": ["directlyproportional"]}], "sol": "Slope 3.5 ÷ 10 = 0.35.\n0.35 × 55 = 19.25 N.\nStraight line through the origin.", "tools": ["calc", "desmos"], "desmos": [{"type": "table", "columns": [{"latex": "x_1", "values": ["10", "20", "30", "40"]}, {"latex": "y_1", "values": ["3.5", "7", "10.5", "14"]}]}, "y_1\\sim ux_1"]}, {"kind": "mcq", "text": "Measured g at distances r from Earth's centre (R = Earth's radius): r = R → 10 m/s², 2R → 2.5 m/s², 4R → 0.63 m/s². Which relationship fits?", "opts": ["g ∝ 1 ÷ r", "g ∝ 1 ÷ r²", "g ∝ r", "g is constant"], "correct": 1, "tag": "", "sol": "Doubling r divides g by 4; ×4 divides by 16. [2.6.A]", "tools": ["desmos"], "desmos": [{"type": "table", "columns": [{"latex": "x_1", "values": ["1", "2", "4"]}, {"latex": "y_1", "values": ["10", "2.5", "0.63"]}]}]}, {"kind": "blank", "p": "A 0.20 kg stone is whirled on a 0.50 m string at different speeds:\nv (m/s): 2, 4, 6   →   T (N): 1.6, 6.4, 14.4", "tag": "", "marks": "", "flat": [{"t": "When v doubles, T is multiplied by __B1__", "a": {"B1": "4"}}, {"t": "T ÷ v² = __B1__ kg/m", "a": {"B1": "0.4"}}, {"t": "Predicted T at v = 5 m/s = __B1__ N", "a": {"B1": "10"}}], "sol": "6.4 ÷ 1.6 = 4.\n1.6 ÷ 4 = 0.4 (= m ÷ r = 0.20 ÷ 0.50).\n0.4 × 25 = 10 N.", "tools": ["calc", "desmos"], "desmos": [{"type": "table", "columns": [{"latex": "x_1", "values": ["2", "4", "6"]}, {"latex": "y_1", "values": ["1.6", "6.4", "14.4"]}]}, "y_1\\sim cx_1^2"]}, {"kind": "mcq", "text": "Springs P and Q are loaded: P stretches 2 cm, 4 cm, 6 cm for 1, 2, 3 N; Q stretches 1 cm, 2 cm, 3 cm for the same loads. Which is correct?", "opts": ["neither obeys Hooke's law", "P is stiffer: k_P = 2k_Q", "they have the same k", "Q is stiffer: k_Q = 2k_P"], "correct": 3, "tag": "", "sol": "k_P = 50 N/m, k_Q = 100 N/m. [2.8.A]"}, {"kind": "mcq", "text": "Satellites around one planet: R = 1 unit → T = 1 unit; R = 2 → T ≈ 2.83; R = 4 → T = 8. The pattern is", "opts": ["T ∝ R³", "T ∝ R", "T² ∝ R³", "T² ∝ R"], "correct": 2, "tag": "", "sol": "2.83² = 8 = 2³; 8² = 64 = 4³. [2.9.B]"}, {"kind": "mcq", "text": "A trolley on a smooth ramp: θ = 30° gives a = 5.0 m/s²; θ = 90° gives 10 m/s²; the relationship is a = g sin θ. Predict a for sin θ = 0.80.", "opts": ["6.0 m/s²", "4.0 m/s²", "8.0 m/s²", "10 m/s²"], "correct": 2, "tag": "", "sol": "10 × 0.80 = 8.0 m/s². [2.5.A]"}, {"kind": "mcq", "text": "A cart's acceleration halves when a 2 kg load is added (same net force). The cart's mass is", "opts": ["4 kg", "0.5 kg", "1 kg", "2 kg"], "correct": 3, "tag": "", "sol": "m + 2 = 2m, m = 2 kg. [2.5.A]"}]}, {"id": "s19", "label": "Test C", "sub": "Test C — Communicating", "slides": [{"kind": "mcq", "text": "Which of these should NOT be drawn as a force on a free-body diagram?", "opts": ["friction", "tension", "ma", "the normal force"], "correct": 2, "tag": "", "sol": "ma is the result of the net force, not a force exerted by an object. [2.2.B]"}, {"kind": "mcq", "text": "The coefficient of friction μ has units of", "opts": ["N/kg", "none (it is dimensionless)", "N", "m/s²"], "correct": 1, "tag": "", "sol": "μ = F_f ÷ F_N: N ÷ N. [2.7.A]"}, {"kind": "mcq", "text": "A student writes: 'The weight of a book and the normal force on it are a Newton's third-law pair.' What is wrong?", "opts": ["They act on the same object and are different types of force", "The normal force is not a real force", "Nothing is wrong", "They are never equal"], "correct": 0, "tag": "", "sol": "Third-law pairs act on different objects and are the same type. [2.3.A]"}, {"kind": "mcq", "text": "m = 2.5 kg and a = 3.24 m/s². F = ma is best reported as", "opts": ["8.100 N", "8.10 N", "8.1 N", "8 N"], "correct": 2, "tag": "", "sol": "2.5 has 2 significant figures, so give 2."}, {"kind": "mcq", "text": "Up is positive. A 60 kg person is in a lift accelerating downward at 2 m/s². Which equation is set up correctly?", "opts": ["F_N + 600 = 60 × (−2)", "F_N = 600 + 120", "F_N − 600 = 60 × (−2)", "F_N − 600 = 60 × 2"], "correct": 2, "tag": "", "sol": "Downward acceleration is negative: F_N = 480 N. [2.6.B]"}, {"kind": "mcq", "text": "Which statement about circular motion is correct?", "opts": ["A centripetal force arrow is added to the FBD as an extra force", "An outward centrifugal force acts in an inertial frame", "'Centripetal force' is the net force toward the centre, supplied by real forces", "At constant speed the acceleration is zero"], "correct": 2, "tag": "", "sol": "Real forces (tension, friction, gravity, normal) add to a net force toward the centre; no extra arrow is drawn. [2.9.A]"}, {"kind": "mcq", "text": "A crate is pushed with a slowly increasing horizontal force until it slides. The graph of friction against push", "opts": ["is constant from the start", "keeps rising after sliding begins", "rises along friction = push to μ_sF_N, then drops to a lower constant μ_kF_N", "drops first, then rises"], "correct": 2, "tag": "", "sol": "Static friction matches the push until its maximum. [2.7.B]"}, {"kind": "mcq", "text": "Which is the correct statement of Newton's second law for a system?", "opts": ["a = m ÷ F", "ΣF = 0 for every moving object", "a_sys = ΣF_ext ÷ m_sys", "F = mv"], "correct": 2, "tag": "", "sol": "Only external forces change the centre-of-mass motion. [2.5.A]"}, {"kind": "blank", "p": "Spot the error: a student calculates that the gravitational force on a 500 g mango is 5000 N.", "tag": "", "marks": "", "flat": [{"t": "Correct mass = __B1__ kg", "a": {"B1": "0.5"}}, {"t": "Correct F_g = __B1__ N", "a": {"B1": "5"}}, {"t": "The student forgot to convert grams to __B1__ (kilograms / newtons).", "a": {"B1": "kilograms"}, "expr": "words", "accept": ["kg", "kilogram"]}], "sol": "500 g = 0.5 kg.\n0.5 × 10 = 5 N.\nAlways use kg in F = mg."}, {"kind": "blank", "p": "An FBD of a 3.0 kg block hanging from a spring balance in a lift shows the spring force as 36 N upward. Up is positive.", "tag": "", "marks": "", "flat": [{"t": "F_g = __B1__ N", "a": {"B1": "30"}}, {"t": "Net force = __B1__ N", "a": {"B1": "6"}}, {"t": "a = __B1__ m/s²", "a": {"B1": "2"}}, {"t": "The lift's acceleration is __B1__ (upward / downward).", "a": {"B1": "upward"}, "expr": "words", "accept": ["up", "upwards"]}], "sol": "3.0 × 10 = 30 N.\n36 − 30 = +6 N.\n6 ÷ 3.0 = 2 m/s².\nPositive = upward. [2.2.B]"}]}, {"id": "s20", "label": "Test D", "sub": "Test D — Applying physics in real-life contexts", "slides": [{"kind": "mcq", "text": "A wicketkeeper stops a 0.16 kg ball moving at 30 m/s in 0.050 s. The average force of the gloves on the ball is", "opts": ["0.24 N", "96 N", "4.8 N", "960 N"], "correct": 1, "tag": "", "sol": "a = 30 ÷ 0.050 = 600 m/s²; F = 0.16 × 600 = 96 N.", "tools": ["calc"]}, {"kind": "mcq", "text": "A seat belt brings a 60 kg passenger from 15 m/s to rest in 0.10 s. The average force is", "opts": ["900 N", "90 N", "150 N", "9000 N"], "correct": 3, "tag": "", "sol": "a = 150 m/s²; F = 60 × 150 = 9000 N.", "tools": ["calc"]}, {"kind": "mcq", "text": "A student calculates that a 1500 kg car going round a 50 m radius roundabout at 10 m/s needs 30 000 N of friction. Is this reasonable?", "opts": ["No: mv² ÷ r = 1500 × 100 ÷ 50 = 3000 N", "Yes, the calculation is right", "No, it needs no friction at constant speed", "No, it needs 300 000 N"], "correct": 0, "tag": "", "sol": "30 000 N would need μ_s = 2, impossible for tyres; the answer is 3000 N (μ_s = 0.2 is enough).", "tools": ["calc"]}, {"kind": "mcq", "text": "A Mumbai local train accelerates at 1.0 m/s². A standing 60 kg passenger does not slip. The friction from the floor on her shoes is", "opts": ["60 N backward", "zero", "600 N forward", "60 N forward"], "correct": 3, "tag": "", "sol": "F = ma = 60 N in the direction of the acceleration.", "tools": ["calc"]}, {"kind": "mcq", "text": "A bathroom scale in a lift reads 20% more than a student's weight. The lift is", "opts": ["accelerating downward at 2 m/s²", "accelerating upward at 2 m/s²", "moving upward at a constant 2 m/s", "in free fall"], "correct": 1, "tag": "", "sol": "F_N = 1.2mg ⇒ a = 0.2g = 2 m/s² upward."}, {"kind": "blank", "p": "An auto-rickshaw (400 kg) takes a flat curve of radius 30 m on a wet road where μ_s = 0.30.", "tag": "", "marks": "", "flat": [{"t": "Maximum friction available = __B1__ N", "a": {"B1": "1200"}}, {"t": "Maximum safe speed = __B1__ m/s", "a": {"B1": "9.49"}, "expr": "approx"}, {"t": "= __B1__ km/h", "a": {"B1": "34.2"}, "expr": "approx"}, {"t": "Is 12 m/s safe? __B1__ (yes / no)", "a": {"B1": "no"}, "expr": "words", "accept": ["n"]}], "sol": "0.30 × 4000 = 1200 N.\nv² = μ_s g r = 90, v ≈ 9.49 m/s.\n× 3.6 ≈ 34.2 km/h.\n12 > 9.49: it would skid.", "tools": ["calc"]}, {"kind": "blank", "p": "An office lift (lift + passengers 800 kg) hangs from a cable with tension 9600 N.", "tag": "", "marks": "", "flat": [{"t": "Net force = __B1__ N", "a": {"B1": "1600"}}, {"t": "Acceleration = __B1__ m/s²", "a": {"B1": "2"}}, {"t": "The acceleration points __B1__ (up / down).", "a": {"B1": "up"}, "expr": "words", "accept": ["upward", "upwards"]}], "sol": "9600 − 8000 = 1600 N.\n1600 ÷ 800 = 2 m/s².\nT > mg.", "tools": ["calc"]}, {"kind": "blank", "p": "Workers push a 60 kg crate up a 30° loading ramp at constant speed; μ_k = 0.20. The push is parallel to the ramp.", "tag": "", "marks": "", "flat": [{"t": "Component of F_g down the ramp = __B1__ N", "a": {"B1": "300"}}, {"t": "Normal force = __B1__ N", "a": {"B1": "520"}, "expr": "approx"}, {"t": "Friction = __B1__ N", "a": {"B1": "104"}, "expr": "approx"}, {"t": "Push needed = __B1__ N", "a": {"B1": "404"}, "expr": "approx"}], "sol": "600 sin 30° = 300 N.\n600 cos 30° ≈ 520 N.\n0.20 × 520 ≈ 104 N (down the ramp).\nConstant speed: 300 + 104 ≈ 404 N.", "fig": "<svg class=\"figsvg\" viewBox=\"0 0 280 170\" role=\"img\"><defs><marker id=\"ah\" viewBox=\"0 0 10 10\" refX=\"9\" refY=\"5\" markerWidth=\"7\" markerHeight=\"7\" orient=\"auto\"><path d=\"M0,1 L10,5 L0,9 z\" class=\"ahd\"/></marker><marker id=\"ahs\" viewBox=\"0 0 10 10\" refX=\"1\" refY=\"5\" markerWidth=\"7\" markerHeight=\"7\" orient=\"auto\"><path d=\"M10,1 L0,5 L10,9 z\" class=\"ahd\"/></marker></defs><path d=\"M20,156 L260.0,156 L260.0,17.4 Z\" style=\"fill:var(--paper-2);stroke:var(--ink);stroke-width:1.5\"/><path class=\"wg\" d=\"M20.0,156.0 L50.0,156.0 A30,30 0 0 0 46.0,141.0 Z\"/><text class=\"al\" x=\"62.5\" y=\"144.6\" text-anchor=\"middle\" dominant-baseline=\"middle\">30°</text><path class=\"ra\" d=\"M260.0,147.0 L251.0,147.0 L251.0,156.0\"/><g transform=\"translate(152.0,79.8) rotate(-30)\"><rect x=\"-17\" y=\"-30\" width=\"34\" height=\"30\" style=\"fill:var(--gold-soft);stroke:var(--ink);stroke-width:1.3\"/><text class=\"lb\" x=\"0\" y=\"-15\" text-anchor=\"middle\" dominant-baseline=\"middle\">60 kg</text></g></svg>", "tools": ["calc"]}, {"kind": "blank", "p": "A weather satellite is to be geostationary (T = 24 h = 86 400 s). Take GM = 4.0 × 10¹⁴ m³/s² for Earth and Earth's radius 6.4 × 10⁶ m.", "tag": "", "marks": "", "flat": [{"t": "Orbit radius R = __B1__ × 10⁷ m", "a": {"B1": "4.23"}, "expr": "approx"}, {"t": "Height above the surface = __B1__ × 10⁷ m", "a": {"B1": "3.59"}, "expr": "approx"}], "sol": "R³ = GMT² ÷ 4π² ≈ 7.56 × 10²²; R ≈ 4.23 × 10⁷ m.\n4.23 × 10⁷ − 0.64 × 10⁷ ≈ 3.59 × 10⁷ m (about 36 000 km).", "tools": ["calc"]}]}];
/* ================= build slide lists ================= */
var SLIDES = {}; SECTIONS.forEach(function(sec){ SLIDES[sec.id]=sec.slides; });
var TAB_DEFS = SECTIONS.map(function(sec){ return {id:sec.id, label:sec.label, sub:sec.sub}; });

/* ================= state ================= */
function blankItem(slide){
  if(slide.kind==='mcq'||slide.kind==='ar'){
    return {status:'unanswered', attempts:0, choice:undefined};
  }
  return {status:'unanswered', curStep:0, stepStates: slide.flat.map(function(){ return {status:'unanswered', attempts:0, inputs:{}}; })};
}
function defaultState(){
  var s={tabs:{}};
  TAB_DEFS.forEach(function(td){
    s.tabs[td.id] = { idx:0, maxReached:0, items: SLIDES[td.id].map(function(sl){ return blankItem(sl); }) };
  });
  return s;
}
var appState = {mode:null, learning:null, quiz:null};
var state = null;      // alias for appState[appState.mode]
var MODE = null;
var activeTab=TAB_DEFS[0].id;

function setMode(m){
  appState.mode = m;
  if(!appState[m]) appState[m] = defaultState();
  state = appState[m];
  MODE = m;
}
/* ================= student accounts (saved on this device) ================= */
var SHEET_KEY='sopaan-ap1-ch2';
var ACC_KEY='sopaan-students-v1';
var storageOK=true;
var MEM={};
function lsGet(k){ var r=null; try{ r=localStorage.getItem(k); }catch(e){ storageOK=false; }
  if(r===null||r===undefined) r=MEM[k]||null; try{ return r?JSON.parse(r):null; }catch(e){ return null; } }
function lsSet(k,v){ var j=JSON.stringify(v); MEM[k]=j; try{ localStorage.setItem(k,j); return true; }catch(e){ storageOK=false; return false; } }
try{ localStorage.setItem('sopaan-probe','1'); localStorage.removeItem('sopaan-probe'); }catch(e){ storageOK=false; }
function hashPin(pin,salt){ var h=2166136261, str=salt+'|'+pin; for(var i=0;i<str.length;i++){ h^=str.charCodeAt(i); h=Math.imul(h,16777619)>>>0; } return h.toString(36); }
function accKey(name,roll){ return (name.trim().toLowerCase().replace(/\s+/g,' ')+'#'+roll.trim().toLowerCase()); }
function accounts(){ return lsGet(ACC_KEY)||{students:{}}; }
var student=null; // {key,name,roll}
var records=[];   // finished-tab history for this student on this sheet
function progKey(){ return SHEET_KEY+'::'+student.key; }

function loadState(){
  appState = {mode:null, learning:null, quiz:null}; records=[]; activeTab=TAB_DEFS[0].id;
  var saved=lsGet(progKey());
  if(!saved) return;
  try{
    ['learning','quiz'].forEach(function(m){
      if(saved[m] && saved[m].tabs){
        var fresh = defaultState();
        TAB_DEFS.forEach(function(td){
          if(saved[m].tabs[td.id] && saved[m].tabs[td.id].items && saved[m].tabs[td.id].items.length===SLIDES[td.id].length){
            fresh.tabs[td.id] = saved[m].tabs[td.id];
          }
        });
        appState[m] = fresh;
      }
    });
    if(saved.mode==='learning' || saved.mode==='quiz') appState.mode = saved.mode;
    if(saved.activeTab && TAB_DEFS.some(function(t){ return t.id===saved.activeTab; })) activeTab = saved.activeTab;
    if(Array.isArray(saved.records)) records = saved.records;
  }catch(e){}
}
function saveState(){
  if(!student) return;
  lsSet(progKey(), {mode:appState.mode, learning:appState.learning, quiz:appState.quiz, activeTab:activeTab, records:records, updated:Date.now()});
  var acc=accounts(); if(acc.students[student.key]){ acc.students[student.key].last=Date.now(); lsSet(ACC_KEY,acc); }
}
function addRecord(mode, tabId, correct, revealed, skipped, total){
  records.unshift({at:Date.now(), mode:mode, tab:tabId, correct:correct, revealed:revealed, skipped:skipped, total:total});
  if(records.length>60) records.length=60;
  saveState();
}
function fmtDate(ms){ try{ return new Date(ms).toLocaleString(undefined,{day:'numeric',month:'short',hour:'2-digit',minute:'2-digit'}); }catch(e){ return ''; } }

function renderWho(){
  var el=document.getElementById('whoBar');
  if(!student){ el.hidden=true; el.innerHTML=''; return; }
  el.hidden=false;
  el.innerHTML='Signed in as <b>'+esc(student.name)+'</b> · Roll '+esc(student.roll)+
    ' <button id="btnRecord">My record</button> <button id="btnSignOut">Sign out</button>';
  document.getElementById('btnRecord').addEventListener('click', renderRecord);
  document.getElementById('btnSignOut').addEventListener('click', signOut);
}
function signOut(){
  saveState(); student=null; state=null; MODE=null;
  var acc=accounts(); delete acc.current; lsSet(ACC_KEY,acc);
  document.getElementById('modePill').hidden=true;
  renderWho(); renderLogin();
}
function signIn(key){
  var acc=accounts(); var st=acc.students[key]; if(!st) return;
  student={key:key, name:st.name, roll:st.roll};
  acc.current=key; st.last=Date.now(); lsSet(ACC_KEY,acc);
  loadState(); renderWho();
  if(appState.mode==='learning' || appState.mode==='quiz'){
    setMode(appState.mode); document.getElementById('modePill').hidden=false; updateModePill();
    showChrome(true); buildTabbar(); renderSlide();
    showToast('Welcome back, '+st.name.split(' ')[0]+'. Picking up where you left off.');
  } else {
    renderModePicker();
  }
}
function renderLogin(msg){
  showChrome(false);
  var acc=accounts(); var keys=Object.keys(acc.students).sort(function(a,b){ return (acc.students[b].last||0)-(acc.students[a].last||0); });
  var h='<div class="login-card"><h2>Student sign-in</h2>'+
    '<p class="lead">Sign in to save your answers, see your record and continue where you left off next time.</p>';
  if(!storageOK) h+='<div class="login-err">This browser is blocking saved data (for example, a private window). You can still practise, but progress will not be kept after you close the page.</div>';
  if(msg) h+='<div class="login-err">'+esc(msg)+'</div>';
  if(keys.length){
    h+='<div class="known"><span class="known-label">Continue as</span>';
    keys.slice(0,6).forEach(function(k){ var st=acc.students[k];
      h+='<button class="known-btn" data-k="'+esc(k)+'"><span>'+esc(st.name)+' <small>· Roll '+esc(st.roll)+'</small></span><small>'+(st.last?'Last active '+fmtDate(st.last):'')+'</small></button>'; });
    h+='</div>';
  }
  h+='<form id="loginForm" novalidate>'+
    '<div class="fld"><label for="lgName">Full name</label><input id="lgName" autocomplete="name" required></div>'+
    '<div class="fld-row"><div class="fld"><label for="lgRoll">Roll no.</label><input id="lgRoll" required></div>'+
    '<div class="fld"><label for="lgPin">4-digit PIN</label><input id="lgPin" type="password" inputmode="numeric" maxlength="4" autocomplete="off" required></div></div>'+
    '<button class="btn btn-primary" type="submit" style="width:100%;">Sign in</button>'+
    '<p class="login-note">New here? Enter your name, roll no. and a PIN you will remember, and your profile is created. Progress is saved on this device, so use the same device and browser to continue.</p>'+
    '</form></div>';
  var wrap=document.getElementById('wrap'); wrap.innerHTML=h;
  wrap.querySelectorAll('.known-btn').forEach(function(b){
    b.addEventListener('click', function(){
      var st=accounts().students[b.dataset.k];
      document.getElementById('lgName').value=st.name; document.getElementById('lgRoll').value=st.roll;
      document.getElementById('lgPin').focus();
    });
  });
  document.getElementById('loginForm').addEventListener('submit', function(e){
    e.preventDefault();
    var name=document.getElementById('lgName').value.trim(), roll=document.getElementById('lgRoll').value.trim(), pin=document.getElementById('lgPin').value.trim();
    if(!name||!roll){ renderLoginErr('Enter your name and roll no.'); return; }
    if(!/^\d{4}$/.test(pin)){ renderLoginErr('Your PIN must be exactly 4 digits.'); return; }
    var k=accKey(name,roll); var acc=accounts();
    if(acc.students[k]){
      if(acc.students[k].pin!==hashPin(pin,k)){ renderLoginErr('That PIN does not match this name and roll no. Try again.'); return; }
    } else {
      acc.students[k]={name:name.replace(/\s+/g,' '), roll:roll, pin:hashPin(pin,k), created:Date.now()};
      lsSet(ACC_KEY,acc);
    }
    signIn(k);
  });
}
function renderLoginErr(m){
  var n=document.getElementById('lgName').value, r=document.getElementById('lgRoll').value;
  renderLogin(m); document.getElementById('lgName').value=n; document.getElementById('lgRoll').value=r; document.getElementById('lgPin').focus();
}
function tabSummary(m){
  var st=appState[m]; if(!st) return null;
  return TAB_DEFS.map(function(td){
    var items=st.tabs[td.id].items, n=items.length;
    var c=items.filter(function(i){return i.status==='correct';}).length;
    var done=items.filter(function(i){return i.status!=='unanswered';}).length;
    return {label:td.label, n:n, done:done, correct:c};
  });
}
function renderRecord(){
  showChrome(false);
  var tabLabel=function(id){ var t=TAB_DEFS.find(function(x){return x.id===id;}); return t?t.label:id; };
  var h='<div class="rec-card"><h2>'+esc(student.name)+'’s record</h2><p class="rec-empty" style="margin:0 0 12px;">Roll '+esc(student.roll)+' · Force and Translational Dynamics</p>';
  ['learning','quiz'].forEach(function(m){
    var sum=tabSummary(m);
    h+='<h3>'+(m==='learning'?'📘 Learning Sheet':'📝 Quiz Mode')+'</h3>';
    if(!sum){ h+='<p class="rec-empty">Not started yet.</p>'; return; }
    h+='<div class="rec-table-wrap"><table class="rec-table"><thead><tr><th>Section</th><th>Progress</th><th>Correct first time</th></tr></thead><tbody>';
    sum.forEach(function(r){ var pct=Math.round(r.done/r.n*100);
      h+='<tr><td>'+r.label+'</td><td><span class="rec-bar"><i style="width:'+pct+'%"></i></span>'+r.done+' / '+r.n+'</td><td>'+(m==='quiz'?'—':r.correct+' / '+r.n)+'</td></tr>'; });
    h+='</tbody></table></div>';
  });
  h+='</div><div class="rec-card"><h3>Finished sections</h3>';
  if(!records.length){ h+='<p class="rec-empty">No sections finished yet. Each time you finish a tab, your score is recorded here.</p>'; }
  else {
    h+='<div class="rec-table-wrap"><table class="rec-table"><thead><tr><th>When</th><th>Mode</th><th>Section</th><th>Score</th></tr></thead><tbody>';
    records.forEach(function(r){ h+='<tr><td>'+fmtDate(r.at)+'</td><td>'+(r.mode==='quiz'?'Quiz':'Learning')+'</td><td>'+tabLabel(r.tab)+'</td><td>'+r.correct+' / '+r.total+(r.mode==='learning'?' <span class="rec-empty">('+r.revealed+' revealed, '+r.skipped+' skipped)</span>':'')+'</td></tr>'; });
    h+='</tbody></table></div>';
  }
  h+='</div><button class="btn btn-primary" id="btnBack">'+(MODE?'Back to practice':'Choose a mode')+'</button>';
  document.getElementById('wrap').innerHTML=h;
  document.getElementById('btnBack').addEventListener('click', function(){
    if(MODE){ showChrome(true); buildTabbar(); renderSlide(); } else renderModePicker();
  });
  window.scrollTo({top:0});
}

/* ================= tab bar ================= */
function buildTabbar(){
  var el=document.getElementById('tabbar');
  el.innerHTML = '<button class="tab-btn'+(activeTab==='theory'?' active':'')+'" data-tab="theory">Theory<span class="tab-count">notes</span></button>' + TAB_DEFS.map(function(t){
    return '<button class="tab-btn'+(t.id===activeTab?' active':'')+'" data-tab="'+t.id+'">'+t.label+'<span class="tab-count">'+SLIDES[t.id].length+'</span></button>';
  }).join('') + '<button class="tab-btn'+(activeTab==='report'?' active':'')+'" data-tab="report">📊 Report<span class="tab-count">pie</span></button>';
  el.querySelectorAll('.tab-btn').forEach(function(btn){
    btn.addEventListener('click', function(){ activeTab=btn.dataset.tab; buildTabbar(); renderSlide(); window.scrollTo({top:0,behavior:'smooth'}); });
  });
}

/* ================= rendering ================= */
function canProceed(item){ return item.status==='correct'||item.status==='revealed'||item.status==='skipped'; }

function renderSlide(){
  if(!state.tabs[activeTab]){ activeTab=TAB_DEFS[0].id; }
  var ts = state.tabs[activeTab];
  var slides = SLIDES[activeTab];
  if(ts.idx>=slides.length||ts.idx<0) ts.idx=0;
  var idx = ts.idx;
  var slide = slides[idx];
  var item = ts.items[idx];

  var tdef=TAB_DEFS.find(function(t){return t.id===activeTab;});
  document.getElementById('spLabel').textContent = tdef.label+' · Question '+(idx+1)+' of '+slides.length;
  document.getElementById('secSub').textContent = tdef.label+' — '+tdef.sub;
  document.getElementById('spFill').style.width = Math.round(((idx)/(Math.max(slides.length-1,1)))*100)+'%';

  var h='<div class="qcard">';
  if(slide.kind==='mcq' || slide.kind==='ar'){
    h += renderChoiceBody(slide, item, idx);
  } else {
    h += renderBlankBody(slide, item, idx);
  }
  h += '<div class="feedback" id="feedbackBox"></div>';
  if(MODE==='learning' && (item.status==='correct'||item.status==='revealed')) h += solutionHTML(slide);
  h += '</div>';

  document.getElementById('wrap').innerHTML = h;
  wireSlideEvents(slide, item, idx);
  restoreFeedback(item);
  renderNavbar(item);
  updateFab();
  saveState();
}

function solutionHTML(slide){
  if(!slide.sol) return '';
  return '<div class="solution"><div class="sol-h">Solution</div>'+slide.sol.split('\n').map(function(l){ return '<div class="sol-line">'+fr(esc(l))+'</div>'; }).join('')+'</div>';
}
var LETTERS=['a','b','c','d','e','f'];
function chosenHTML(slide,item){
  var opts = slide.kind==='mcq' ? slide.opts : AR_OPTIONS;
  if(item.choice===undefined) return '';
  var ok=item.choice===slide.correct;
  var h='<div class="chosen '+(ok?'ok':'bad')+'"><b>Your answer:</b> ('+LETTERS[item.choice]+') '+fr(esc(opts[item.choice]))+(ok?' ✓':' ✗')+'</div>';
  if(!ok) h+='<div class="chosen ok"><b>Correct answer:</b> ('+LETTERS[slide.correct]+') '+fr(esc(opts[slide.correct]))+'</div>';
  return h;
}
function renderChoiceBody(slide, item, idx){
  var h='<div class="qhead"><div class="qnum">'+(idx+1)+'</div>';
  if(slide.kind==='mcq'){
    h += '<div class="qtext">'+fr(esc(slide.text))+(slide.tag?'<span class="qtag">'+esc(slide.tag)+'</span>':'')+'</div>';
  } else {
    h += '<div class="qtext"><span class="qtag" style="margin-left:0;margin-right:6px;">A / R</span>Assertion (A): '+fr(esc(slide.a))+'<br>Reason (R): '+fr(esc(slide.r))+(slide.tag?'<span class="qtag">'+esc(slide.tag)+'</span>':'')+'</div>';
  }
  h += '</div>';
  if(slide.fig) h += '<div class="fig">'+slide.fig+'</div>';
  var opts = slide.kind==='mcq' ? slide.opts : AR_OPTIONS;
  if(MODE==='quiz') h += '<div class="quiz-hint">Quiz mode — pick an option. The correct answer is revealed once you finish this tab.</div>';
  var locked = MODE==='learning' && (item.status==='correct' || item.status==='revealed');
  h += '<div class="options">';
  opts.forEach(function(opt,i){
    var cls='opt';
    if(locked){
      if(i===slide.correct) cls+=' is-correct';
      else if(item.choice===i) cls+=' is-wrong';
      cls+=' locked';
    }
    if(item.choice===i) cls+=' is-chosen';
    h += '<label class="'+cls+'"><input type="radio" name="choice" value="'+i+'" '+(item.choice===i?'checked':'')+' '+(locked?'disabled':'')+'> <span class="opt-l">('+LETTERS[i]+')</span> <span class="opt-t">'+fr(esc(opt))+'</span>'+(item.choice===i?'<span class="opt-tag">'+(locked?(i===slide.correct?'Your answer ✓':'Your answer ✗'):'Selected')+'</span>':'')+'</label>';
  });
  h += '</div>';
  if(locked) h += chosenHTML(slide,item);
  return h;
}

function renderBlankBody(slide, item, idx){
  var h='<div class="qhead"><div class="qnum">'+(idx+1)+'</div><div class="qtext">';
  if(slide.kind==='case'){ h += '<b>'+esc(slide.title)+'.</b> '+esc(slide.body); }
  else { var pp=fr(esc(slide.p)).split('\n'); h += pp[0]+pp.slice(1).map(function(x){return '<span class="datline">'+x+'</span>';}).join(''); }
  h += (slide.tag?'<span class="qtag">'+esc(slide.tag)+'</span>':'')+'</div>';
  if(slide.marks) h += '<div class="marks-pill">'+slide.marks+'</div>';
  h += '</div>';
  if(slide.fig) h += '<div class="fig">'+slide.fig+'</div>';

  var total = slide.flat.length;
  var hasExpr = slide.flat.some(function(s){ return s.expr===true; });
  var hasFrac = slide.flat.some(function(s){ return ['fv','fe','fl','fm','fi','flist'].indexOf(s.expr)>=0; });
  var blankCount=0; slide.flat.forEach(function(s){ blankCount+=Object.keys(s.a).length; });

  if(MODE==='quiz'){
    h += '<div class="step-badge">'+blankCount+' blank'+(blankCount===1?'':'s')+' in this question</div>';
    h += '<div class="quiz-hint">Quiz mode — fill in what you can. Correct answers are revealed once you finish this tab.</div>';
    if(hasFrac) h += '<div class="quiz-hint">Type fractions like <b>3/4</b> and mixed numbers like <b>2 3/4</b> (whole number, space, fraction).</div>';
    if(hasExpr) h += '<div class="quiz-hint">Type answers like <b>2x-5</b>, <b>x^2-4</b> or <b>3+2i</b>. Use ^ for powers, | | for absolute value and pi for π. Any equivalent form is accepted.</div>';
    h += '<div class="steps">';
    for(var qi=0; qi<total; qi++){
      var qstep = slide.flat[qi];
      var qss = item.stepStates[qi];
      if(qstep.partLabel) h += '<div class="subpart-label">'+esc(qstep.partLabel)+'</div>';
      if(qstep.orDivider) h += '<div class="or-divider">OR</div>';
      var qline = fr(qstep.t);
      Object.keys(qstep.a).forEach(function(bkey){
        var val = qss.inputs[bkey]||'';
        var inp='<input class="blank-input'+(['fv','fe','fl','fm','fi','dec'].indexOf(qstep.expr)>=0?' fr':(qstep.expr==='flist'||qstep.expr==='dlist'||qstep.expr==='glist')?' wide':qstep.expr===true?' expr':(qstep.expr==='words'||qstep.expr==='list'||qstep.expr==='expanded'||qstep.expr==='set'||qstep.expr==='primes'||qstep.expr==='trans'||qstep.expr==='rot'?' wide':''))+'" data-step="'+qi+'" data-bkey="'+bkey+'" value="'+esc(val)+'">';
        qline = qline.replace('__'+bkey+'__', inp);
      });
      if(qstep.fig) h += '<div class="fig">'+qstep.fig+'</div>';
      h += '<div class="step-line">'+qline+'</div>';
    }
    h += '</div>';
    return h;
  }

  if(hasFrac) h += '<div class="quiz-hint">Type fractions like <b>3/4</b> and mixed numbers like <b>2 3/4</b> (whole number, space, fraction).</div>';
  if(hasExpr) h += '<div class="quiz-hint">Type answers like <b>2x-5</b>, <b>x^2-4</b> or <b>3+2i</b>. Use ^ for powers, | | for absolute value and pi for π. Any equivalent form is accepted.</div>';
  var locked = item.status==='correct' || item.status==='revealed';
  var upto = locked ? total-1 : item.curStep;
  h += '<div class="step-badge">Step '+(Math.min(item.curStep,total-1)+1)+' of '+total+'</div>';
  h += '<div class="steps">';
  for(var i=0;i<=upto;i++){
    var step = slide.flat[i];
    var ss = item.stepStates[i];
    if(step.partLabel) h += '<div class="subpart-label">'+esc(step.partLabel)+'</div>';
    if(step.orDivider) h += '<div class="or-divider">OR</div>';
    var resolved = ss.status==='correct' || ss.status==='revealed';
    var line = fr(step.t);
    Object.keys(step.a).forEach(function(bkey){
      var fs = ss.inputs['fs_'+bkey];
      var cls = fs==='correct'?'is-correct':(fs==='wrong'?'is-wrong':'');
      var val = ss.inputs[bkey]||'';
      var dis = resolved ? 'disabled':'';
      var inp='<input class="blank-input '+cls+(['fv','fe','fl','fm','fi','dec'].indexOf(step.expr)>=0?' fr':(step.expr==='flist'||step.expr==='dlist'||step.expr==='glist')?' wide':step.expr===true?' expr':(step.expr==='words'||step.expr==='list'||step.expr==='expanded'||step.expr==='set'||step.expr==='primes'||step.expr==='trans'||step.expr==='rot'?' wide':''))+'" data-step="'+i+'" data-bkey="'+bkey+'" value="'+esc(val)+'" '+dis+'>';
      line = line.replace('__'+bkey+'__', inp);
    });
    if(step.fig) h += '<div class="fig">'+step.fig+'</div>';
    h += '<div class="step-line'+(resolved?' resolved':'')+'">'+line+'</div>';
    if(ss.status==='revealed'){
      var reveals=[];
      Object.keys(step.a).forEach(function(bkey){ reveals.push(bkey+' = '+esc(step.a[bkey])); });
      h += '<div class="reveal-note">correct: '+reveals.join(', ')+'</div>';
    }
  }
  h += '</div>';
  return h;
}

var __flash=null;
function restoreFeedback(item){
  var fb=document.getElementById('feedbackBox'); if(!fb) return;
  if(__flash){ fb.className='feedback show '+__flash.c; fb.innerHTML=__flash.h; __flash=null; return; }
  if(MODE==='quiz'){ fb.className='feedback'; fb.innerHTML=''; return; }
  if(item.status==='correct'){ fb.className='feedback show ok'; fb.innerHTML='<b>All done — correct!</b>'; }
  else if(item.status==='revealed'){ fb.className='feedback show reveal'; fb.innerHTML='<b>Answer revealed above.</b> Move on whenever you’re ready.'; }
  else if(item.status==='skipped'){ fb.className='feedback show retry'; fb.innerHTML='Skipped — you can answer it now and press <b>Check</b>, or come back later from the Question Palette.'; }
  else { fb.className='feedback'; fb.innerHTML=''; }
}

function slideIsAnswered(slide,item){
  if(slide.kind==='mcq'||slide.kind==='ar') return item.choice!==undefined;
  return item.stepStates.some(function(ss){ return Object.keys(ss.inputs).some(function(k){ return k.indexOf('fs_')!==0 && ss.inputs[k] && String(ss.inputs[k]).trim()!==''; }); });
}
function renderNavbar(item){
  var ts = state.tabs[activeTab];
  var slides = SLIDES[activeTab];
  var slide = slides[ts.idx];
  var isLast = ts.idx === slides.length-1;
  var h='';
  h += '<button class="btn" id="btnPrev" '+(ts.idx===0?'disabled':'')+'>&larr; Previous</button>';

  if(MODE==='quiz'){
    h += '<button class="btn" id="btnSkip">Skip</button>';
    h += '<span class="spacer"></span>';
    h += '<button class="btn btn-primary" id="btnNext">'+(isLast?'Finish':'Next →')+'</button>';
  } else {
    h += '<button class="btn" id="btnSkip" '+(item.status!=='unanswered'?'disabled':'')+'>Skip</button>';
    h += '<span class="spacer"></span>';
    h += '<button class="btn btn-primary" id="btnCheck" '+((item.status!=='unanswered'&&item.status!=='skipped')?'disabled':'')+'>Check</button>';
    h += '<button class="btn btn-primary" id="btnNext" '+(canProceed(item)?'':'disabled')+'>'+(isLast?'Finish':'Next →')+'</button>';
  }
  document.getElementById('navbarInner').innerHTML = h;

  document.getElementById('btnPrev').addEventListener('click', function(){ if(ts.idx>0){ ts.idx--; renderSlide(); } });

  if(MODE==='quiz'){
    document.getElementById('btnSkip').addEventListener('click', function(){
      item.status='skipped';
      advanceQuiz(ts, slides);
    });
    document.getElementById('btnNext').addEventListener('click', function(){
      item.status = slideIsAnswered(slide,item) ? 'answered' : 'unanswered';
      advanceQuiz(ts, slides);
    });
  } else {
    document.getElementById('btnSkip').addEventListener('click', function(){
      if(item.status==='unanswered'){ item.status='skipped'; renderSlide(); }
    });
    document.getElementById('btnNext').addEventListener('click', function(){
      if(!canProceed(item)) return;
      if(ts.idx < slides.length-1){ ts.idx++; ts.maxReached=Math.max(ts.maxReached, ts.idx); renderSlide(); }
      else { renderFinished(); }
    });
    document.getElementById('btnCheck').addEventListener('click', function(){ handleCheck(); });
  }
}
function advanceQuiz(ts, slides){
  if(ts.idx < slides.length-1){ ts.idx++; ts.maxReached=Math.max(ts.maxReached, ts.idx); renderSlide(); }
  else { renderFinished(); }
}

function wireSlideEvents(slide, item, idx){
  document.querySelectorAll('input[type="radio"][name="choice"]').forEach(function(r){
    r.addEventListener('change', function(){ item.choice=parseInt(r.value,10); saveState();
      document.querySelectorAll('.opt').forEach(function(l){ l.classList.remove('is-chosen'); var t=l.querySelector('.opt-tag'); if(t) t.remove(); });
      var lab=r.closest('.opt'); lab.classList.add('is-chosen'); var tg=document.createElement('span'); tg.className='opt-tag'; tg.textContent='Selected'; lab.appendChild(tg); });
  });
  document.querySelectorAll('.blank-input').forEach(function(inp){
    inp.addEventListener('input', function(){
      var si=parseInt(inp.dataset.step,10), bk=inp.dataset.bkey;
      item.stepStates[si].inputs[bk]=inp.value;
      saveState();
    });
  });
}

function handleCheck(){
  var ts = state.tabs[activeTab];
  var slide = SLIDES[activeTab][ts.idx];
  var item = ts.items[ts.idx];
  if(item.status==='skipped') item.status='unanswered';
  var fb = document.getElementById('feedbackBox');

  if(slide.kind==='mcq' || slide.kind==='ar'){
    if(item.choice===undefined){ fb.className='feedback show err'; fb.innerHTML='Please choose an option first.'; return; }
    var ok = item.choice===slide.correct;
    if(ok){
      item.status='correct'; playSuccess();
      fb.className='feedback show ok'; fb.innerHTML='<b>Correct!</b>';
    } else {
      item.attempts=(item.attempts||0)+1;
      if(item.attempts>=2){ item.status='revealed'; playReveal(); }
      else { playWrong(); fb.className='feedback show retry'; fb.innerHTML='<b>Not quite — try again</b> (attempt 1 of 2) <span class="attempts-dots"><span class="used"></span><span></span></span>'; __flash={c:'retry',h:'<b>Not quite — try again</b> (attempt 1 of 2) <span class="attempts-dots"><span class="used"></span><span></span></span>'}; }
    }
    renderSlide();
    return;
  }

  // blank / case
  var step = slide.flat[item.curStep];
  var ss = item.stepStates[item.curStep];
  var blanks = Object.keys(step.a);
  var missing = blanks.some(function(k){ return !ss.inputs[k] || String(ss.inputs[k]).trim()===''; });
  if(missing){ fb.className='feedback show err'; fb.innerHTML='Fill in every blank in this step before checking.'; return; }

  var allGood=true;
  blanks.forEach(function(k){
    var good=answerMatches(ss.inputs[k], step.a[k], step.accept, step.expr);
    ss.inputs['fs_'+k]=good?'correct':'wrong';
    if(!good) allGood=false;
  });

  if(allGood){
    ss.status='correct'; playSuccess();
    advanceStepOrFinish(item, slide);
  } else {
    ss.attempts=(ss.attempts||0)+1;
    if(ss.attempts>=2){
      ss.status='revealed'; playReveal();
      advanceStepOrFinish(item, slide);
    } else {
      playWrong();
      fb.className='feedback show retry';
      fb.innerHTML='<b>Not quite — try again</b> (attempt 1 of 2) <span class="attempts-dots"><span class="used"></span><span></span></span>'; __flash={c:'retry',h:'<b>Not quite — try again</b> (attempt 1 of 2) <span class="attempts-dots"><span class="used"></span><span></span></span>'};
      renderSlide();
      return;
    }
  }
  renderSlide();
}

function advanceStepOrFinish(item, slide){
  var total = slide.flat.length;
  var hasExpr = slide.flat.some(function(s){ return s.expr===true; });
  var hasFrac = slide.flat.some(function(s){ return ['fv','fe','fl','fm','fi','flist'].indexOf(s.expr)>=0; });
  if(item.curStep < total-1){
    item.curStep++;
  } else {
    var anyRevealed = item.stepStates.some(function(ss){ return ss.status==='revealed'; });
    item.status = anyRevealed ? 'revealed' : 'correct';
  }
}

/* ================= palette ================= */
var overlay=document.getElementById('overlay');
function statusOf(tabId,i){
  var ts=state.tabs[tabId];
  if(i>ts.maxReached) return 'locked';
  if(i===ts.idx) return 'current';
  return ts.items[i].status==='unanswered' ? 'locked' : ts.items[i].status;
}
function buildPalette(){
  var slides=SLIDES[activeTab];
  document.getElementById('paletteTitle').textContent = TAB_DEFS.find(function(t){return t.id===activeTab;}).label+' · Question palette';
  var body=document.getElementById('paletteBody');
  var html='';
  for(var i=0;i<slides.length;i++){
    html += '<div class="chip" data-status="'+statusOf(activeTab,i)+'" data-idx="'+i+'">'+(i+1)+'</div>';
  }
  body.innerHTML = html;
  body.querySelectorAll('.chip').forEach(function(chip){
    chip.addEventListener('click', function(){
      var i=parseInt(chip.dataset.idx,10);
      var ts=state.tabs[activeTab];
      if(i>ts.maxReached){ showToast('Finish the earlier questions to unlock this one.'); return; }
      ts.idx=i; closePalette(); renderSlide();
    });
  });
}
function openPalette(){ buildPalette(); overlay.classList.add('show'); }
function closePalette(){ overlay.classList.remove('show'); }
var toastTimer;
function showToast(msg){
  var t=document.getElementById('toast'); t.textContent=msg; t.classList.add('show');
  clearTimeout(toastTimer); toastTimer=setTimeout(function(){ t.classList.remove('show'); },2200);
}
document.getElementById('paletteFab').addEventListener('click', openPalette);
document.getElementById('paletteClose').addEventListener('click', closePalette);
overlay.addEventListener('click', function(e){ if(e.target===overlay) closePalette(); });

function updateFab(){
  var slides=SLIDES[activeTab];
  var done=state.tabs[activeTab].items.filter(function(it){ return it.status==='correct'||it.status==='revealed'||it.status==='skipped'; }).length;
  document.getElementById('fabBadge').textContent = done+'/'+slides.length;
}

/* ================= overall progress + finish ================= */
function updateChapterProgress(){
  var total=0, done=0;
  TAB_DEFS.forEach(function(td){
    state.tabs[td.id].items.forEach(function(it){
      total++;
      if(it.status==='correct'||it.status==='revealed'||it.status==='skipped') done++;
    });
  });
  var pct = total>0 ? Math.round((done/total)*100) : 0;
  document.getElementById('cpFill').style.width=pct+'%';
  document.getElementById('cpLabel').textContent=pct+'% complete';
}
function isSlideCorrect(tabId,i){
  var slide=SLIDES[tabId][i], item=state.tabs[tabId].items[i];
  if(slide.kind==='mcq'||slide.kind==='ar') return item.choice===slide.correct;
  return slide.flat.every(function(step,si){
    var ss=item.stepStates[si];
    return Object.keys(step.a).every(function(k){ return answerMatches(ss.inputs[k], step.a[k], step.accept, step.expr); });
  });
}
function isSlideAttempted(tabId,i){
  var slide=SLIDES[tabId][i], item=state.tabs[tabId].items[i];
  if(slide.kind==='mcq'||slide.kind==='ar') return item.choice!==undefined;
  return slide.flat.some(function(step,si){
    var ss=item.stepStates[si];
    return Object.keys(step.a).some(function(k){ return ss.inputs[k] && String(ss.inputs[k]).trim()!==''; });
  });
}
function slideLabel(slide){
  var t = slide.kind==='case' ? slide.title : (slide.kind==='ar' ? slide.a : (slide.p||slide.text||''));
  t = String(t);
  return t.length>90 ? t.slice(0,90)+'…' : t;
}
function slideAnswerText(slide, item, correctSide){
  if(slide.kind==='mcq'||slide.kind==='ar'){
    var opts = slide.kind==='mcq' ? slide.opts : AR_OPTIONS;
    if(correctSide) return '('+LETTERS[slide.correct]+') '+opts[slide.correct];
    return item.choice!==undefined ? '('+LETTERS[item.choice]+') '+opts[item.choice] : '— not attempted —';
  }
  return slide.flat.map(function(step,si){
    var ss=item.stepStates[si];
    return Object.keys(step.a).map(function(k){
      return correctSide ? step.a[k] : (ss.inputs[k] || '—');
    }).join(', ');
  }).join('  |  ');
}

function renderFinished(){
  if(MODE==='quiz'){ renderQuizResults(); return; }
  var ts=state.tabs[activeTab];
  var correct=ts.items.filter(function(i){return i.status==='correct';}).length;
  var revealed=ts.items.filter(function(i){return i.status==='revealed';}).length;
  var skipped=ts.items.filter(function(i){return i.status==='skipped';}).length;
  var h='<div class="qcard done-card"><div class="big">✨</div><h2>Tab complete</h2>';
  h+='<p style="color:var(--ink-soft);font-size:14px;">You worked through all '+ts.items.length+' questions in this tab.</p>';
  if(!ts.recorded){ ts.recorded=true; addRecord('learning', activeTab, correct, revealed, skipped, ts.items.length); }
  h+='<div class="score-pills">'+
     '<span class="score-pill" style="background:var(--success-soft);color:var(--success);">'+correct+' correct</span>'+
     '<span class="score-pill" style="background:var(--danger-soft);color:var(--danger);">'+revealed+' revealed</span>'+
     '<span class="score-pill" style="background:var(--gold-soft);color:var(--retry-text);">'+skipped+' skipped</span></div>'+
     '<button class="btn btn-primary" id="btnReview">Review from question 1</button></div>';
  document.getElementById('wrap').innerHTML=h;
  document.getElementById('navbarInner').innerHTML='';
  document.getElementById('btnReview').addEventListener('click', function(){ ts.idx=0; ts.recorded=false; renderSlide(); });
  updateChapterProgress(); saveState();
}

function renderQuizResults(){
  var ts=state.tabs[activeTab];
  var slides=SLIDES[activeTab];
  var correctCount=0, attemptedCount=0;
  var rowsHtml = slides.map(function(slide,i){
    var item=ts.items[i];
    var ok=isSlideCorrect(activeTab,i);
    var att=isSlideAttempted(activeTab,i);
    if(ok) correctCount++;
    if(att) attemptedCount++;
    var tagCls = ok?'ok':(att?'bad':'na');
    var tagText = ok?'Correct':(att?'Incorrect':'Not attempted');
    var row='<div class="review-row">';
    row+='<span class="review-tag '+tagCls+'">Q'+(i+1)+' · '+tagText+'</span>';
    row+='<div class="review-q">'+fr(esc(slideLabel(slide)))+'</div>';
    row+='<div class="review-ans"><b>Your answer:</b> '+fr(esc(slideAnswerText(slide,item,false)))+'</div>';
    if(!ok) row+='<div class="review-ans" style="color:var(--success);"><b>Correct answer:</b> '+fr(esc(slideAnswerText(slide,item,true)))+'</div>';
    if(slide.sol) row+='<details class="rev-sol"><summary>Show solution</summary>'+solutionHTML(slide)+'</details>';
    row+='</div>';
    return row;
  }).join('');

  addRecord('quiz', activeTab, correctCount, 0, 0, slides.length);
  var h='<div class="qcard done-card" style="text-align:left;">';
  h+='<div style="text-align:center;"><div class="big">🏁</div><h2>Quiz complete</h2>';
  h+='<p style="color:var(--ink-soft);font-size:14px;">'+correctCount+' / '+slides.length+' correct · '+attemptedCount+' attempted</p></div>';
  h+='<div style="margin-top:16px;">'+rowsHtml+'</div>';
  h+='<div style="text-align:center;margin-top:6px;"><button class="btn btn-primary" id="btnReview">Review from question 1</button></div>';
  h+='</div>';
  document.getElementById('wrap').innerHTML=h;
  document.getElementById('navbarInner').innerHTML='';
  document.getElementById('btnReview').addEventListener('click', function(){ ts.idx=0; renderSlide(); });
  playSuccess();
  updateChapterProgress(); saveState();
}

/* ================= mode picker ================= */
function updateModePill(){
  var btn=document.getElementById('modePill');
  if(!btn) return;
  btn.textContent = MODE==='quiz' ? '📝 Quiz Mode · switch' : '📘 Learning Sheet · switch';
}
function showChrome(show){
  document.querySelector('.tabbar').style.display = show?'':'none';
  document.querySelector('.slide-progress').style.display = show?'':'none';
  document.querySelector('.navbar').style.display = show?'':'none';
  document.getElementById('paletteFab').style.display = show?'':'none';
}
function renderModePicker(){
  showChrome(false);
  var wrap=document.getElementById('wrap');
  wrap.innerHTML =
    '<div class="mode-pick">'+
      '<div class="mode-card" data-pick="learning"><div class="mode-icon">📘</div><h3>Learning Sheet</h3>'+
      '<p>Work through each question step by step with instant feedback — two tries, then the correct value is revealed right there so you can keep moving.</p></div>'+
      '<div class="mode-card" data-pick="quiz"><div class="mode-icon">📝</div><h3>Quiz Mode</h3>'+
      '<p>Attempt every question with no hints along the way. Your score and the full answer key are shown together once you finish the tab — just like the real exam.</p></div>'+
    '</div>';
  wrap.querySelectorAll('[data-pick]').forEach(function(card){
    card.addEventListener('click', function(){
      setMode(card.dataset.pick); activeTab='theory';
      document.getElementById('modePill').hidden=false;
      updateModePill();
      showChrome(true);
      buildTabbar();
      renderSlide();
    });
  });
}
document.getElementById('modePill').addEventListener('click', function(){
  if(!appState.mode){ return; }
  setMode(appState.mode==='quiz' ? 'learning' : 'quiz');
  updateModePill();
  showChrome(true);
  buildTabbar();
  renderSlide();
});

/* ================= boot ================= */
var _origRenderSlide = renderSlide;
renderSlide = function(){ _origRenderSlide(); updateChapterProgress(); updateModePill(); };


/* ================= theory tab ================= */
function renderTheory(){
  var wrap=document.getElementById('wrap');
  wrap.innerHTML='<div class="theory">'+fr(THEORY)+'</div>';
  document.querySelector('.slide-progress').style.display='none';
  document.querySelector('.navbar').style.display='none';
  document.getElementById('paletteFab').style.display='none';
  document.getElementById('secSub').textContent='Theory — notes, key ideas and worked examples';
  wrap.querySelectorAll('[data-go]').forEach(function(b){ b.addEventListener('click',function(){ activeTab=b.dataset.go; buildTabbar(); renderSlide(); window.scrollTo({top:0,behavior:'smooth'}); }); });
  wrap.querySelectorAll('[data-jump]').forEach(function(b){ b.addEventListener('click',function(){ var t=document.getElementById(b.dataset.jump); if(t) t.scrollIntoView({behavior:'smooth',block:'start'}); }); });
}
var _rsTheory = renderSlide;
renderSlide = function(){
  if(activeTab==='theory'){ renderTheory(); buildTabbar(); updateChapterProgress(); updateModePill(); saveState(); return; }
  document.querySelector('.slide-progress').style.display='';
  document.querySelector('.navbar').style.display='';
  document.getElementById('paletteFab').style.display='';
  _rsTheory();
};


/* ================= MYP criterion report ================= */
var CRIT_COL={A:'var(--accent-text)',B:'var(--gold)',C:'#8A6FC4',D:'#2F9AA0'};
function critStats(){
  return REPORT.map(function(r){
    var tabId=r[0], slides=SLIDES[tabId], ts=state&&state.tabs[tabId];
    var c=0,w=0,n=0;
    slides.forEach(function(sl,i){
      if(!ts||!ts.items[i]){ n++; return; }
      var it=ts.items[i];
      if(MODE==='learning'){
        if(it.status==='correct') c++; else if(it.status==='revealed') w++; else n++;
      } else {
        if(isSlideCorrect(tabId,i)) c++; else if(isSlideAttempted(tabId,i)) w++; else n++;
      }
    });
    var tot=slides.length, pct=tot?Math.round(c/tot*100):0;
    var lvl=Math.round(c/Math.max(tot,1)*8);
    return {tab:tabId,letter:r[1],name:r[2],c:c,w:w,n:n,tot:tot,pct:pct,lvl:lvl};
  });
}
function arcPath(cx,cy,r,a0,a1){
  if(a1-a0>=Math.PI*2-1e-6){ return 'M'+(cx-r)+','+cy+' a'+r+','+r+' 0 1,0 '+(2*r)+',0 a'+r+','+r+' 0 1,0 '+(-2*r)+',0 Z'; }
  var x0=cx+r*Math.sin(a0), y0=cy-r*Math.cos(a0), x1=cx+r*Math.sin(a1), y1=cy-r*Math.cos(a1);
  return 'M'+cx+','+cy+' L'+x0.toFixed(2)+','+y0.toFixed(2)+' A'+r+','+r+' 0 '+((a1-a0)>Math.PI?1:0)+',1 '+x1.toFixed(2)+','+y1.toFixed(2)+' Z';
}
function pieSVG(parts,size,hole,center,sub){
  var tot=parts.reduce(function(s,p){return s+p.v;},0), cx=size/2, cy=size/2, r=size/2-4, a=0, h='';
  if(!tot){ h+='<circle cx="'+cx+'" cy="'+cy+'" r="'+r+'" style="fill:var(--paper-2);stroke:var(--rule)"/>'; }
  parts.forEach(function(p){ if(!p.v) return; var b=a+p.v/tot*Math.PI*2; h+='<path d="'+arcPath(cx,cy,r,a,b)+'" style="fill:'+p.col+';stroke:var(--card);stroke-width:2"><title>'+esc(p.label)+': '+p.v+'</title></path>'; a=b; });
  if(hole) h+='<circle cx="'+cx+'" cy="'+cy+'" r="'+(r*hole)+'" style="fill:var(--card)"/>';
  if(center) h+='<text x="'+cx+'" y="'+(cy-(sub?4:0))+'" text-anchor="middle" dominant-baseline="middle" style="fill:var(--ink);font:700 '+(size>150?22:15)+'px Fraunces,serif">'+center+'</text>';
  if(sub) h+='<text x="'+cx+'" y="'+(cy+16)+'" text-anchor="middle" style="fill:var(--ink-soft);font:600 11px \'Source Sans 3\',sans-serif">'+sub+'</text>';
  return '<svg viewBox="0 0 '+size+' '+size+'" width="'+size+'" height="'+size+'" role="img">'+h+'</svg>';
}
function band(l){ return l===0?'0':(l<=2?'1–2':(l<=4?'3–4':(l<=6?'5–6':'7–8'))); }
function renderReport(){
  var st=critStats(), totC=0, totQ=0;
  st.forEach(function(s){ totC+=s.c; totQ+=s.tot; });
  var h='<div class="theory">';
  h+='<section class="note"><h2>Chapter test report</h2><p class="lt">'+(MODE==='quiz'?'<b>Quiz mode</b> results: answers are marked when you finish each test tab.':'<b>Learning mode</b> results: a question counts as correct only if you got it without the answer being revealed. Switch to Quiz mode for an exam-style score.')+'</p>';
  h+='<div class="rep-top"><div class="rep-pie">'+pieSVG(st.map(function(s){return {v:s.c,col:CRIT_COL[s.letter],label:'Criterion '+s.letter};}),200,0.55,totC+'/'+totQ,'correct')+'</div>';
  h+='<div class="rep-legend"><div class="rep-cap">Marks earned, by criterion</div>'+st.map(function(s){ return '<div class="rep-li"><span class="sw" style="background:'+CRIT_COL[s.letter]+'"></span><b>'+s.letter+'</b>&nbsp;'+esc(s.name)+'<span class="rep-n">'+s.c+' / '+s.tot+'</span></div>'; }).join('')+'</div></div></section>';
  h+='<div class="rep-grid">'+st.map(function(s){
    return '<div class="rep-card"><div class="rep-h"><span class="crit" style="background:'+CRIT_COL[s.letter]+'">'+s.letter+'</span>'+esc(s.name)+'</div>'+
      '<div class="rep-row">'+pieSVG([{v:s.c,col:'var(--success)',label:'Correct'},{v:s.w,col:'var(--danger)',label:'Incorrect'},{v:s.n,col:'var(--locked)',label:'Not attempted'}],120,0.5,s.pct+'%')+
      '<div class="rep-stats"><div><span class="sw" style="background:var(--success)"></span>Correct <b>'+s.c+'</b></div><div><span class="sw" style="background:var(--danger)"></span>Incorrect <b>'+s.w+'</b></div><div><span class="sw" style="background:var(--locked)"></span>Not attempted <b>'+s.n+'</b></div>'+
      '<div class="rep-lvl">Indicative level <b>'+s.lvl+'</b> / 8 <span>(band '+band(s.lvl)+')</span></div></div></div>'+
      '<button class="hub-btn" data-go="'+s.tab+'">Open Test '+s.letter+' →</button></div>';
  }).join('')+'</div>';
  h+='<p class="rep-note">Indicative level = fraction of questions correct × 8, rounded. It is a practice guide only; your teacher awards the real MYP criterion levels.</p></div>';
  var wrap=document.getElementById('wrap'); wrap.innerHTML=h;
  document.querySelector('.slide-progress').style.display='none';
  document.querySelector('.navbar').style.display='none';
  document.getElementById('paletteFab').style.display='none';
  document.getElementById('secSub').textContent='Report — chapter test results by MYP criterion';
  wrap.querySelectorAll('[data-go]').forEach(function(b){ b.addEventListener('click',function(){ activeTab=b.dataset.go; buildTabbar(); renderSlide(); window.scrollTo({top:0,behavior:'smooth'}); }); });
}
var _rsReport = renderSlide;
renderSlide = function(){
  if(activeTab==='report'){ renderReport(); buildTabbar(); updateChapterProgress(); updateModePill(); saveState(); return; }
  _rsReport();
};


/* ================= skipped-question return ================= */
function firstSkippedIdx(ts){
  for(var i=0;i<ts.items.length;i++){
    var it=ts.items[i];
    if(MODE==='quiz'){ if(!isSlideAttempted(activeTab,i)) return i; }
    else if(it.status==='skipped'||it.status==='unanswered') return i;
  }
  return -1;
}
function skippedList(ts){
  var out=[]; for(var i=0;i<ts.items.length;i++){ var it=ts.items[i];
    if(MODE==='quiz' ? !isSlideAttempted(activeTab,i) : (it.status==='skipped'||it.status==='unanswered')) out.push(i); }
  return out;
}
function renderSkipGate(ts){
  var list=skippedList(ts);
  var h='<div class="qcard done-card"><div class="big">⏭️</div><h2>You skipped '+list.length+' question'+(list.length>1?'s':'')+'</h2>'+
    '<p style="color:var(--ink-soft);font-size:14px;">Answer them now, or submit the tab as it is. Answers are marked only when you submit.</p>'+
    '<div class="skip-chips">'+list.map(function(i){ return '<button class="chip skip-go" data-i="'+i+'">Q'+(i+1)+'</button>'; }).join('')+'</div>'+
    '<div class="skip-btns"><button class="btn btn-primary" id="btnGoSkipped">Answer skipped questions</button><button class="btn" id="btnSubmitAnyway">Submit anyway</button></div></div>';
  document.getElementById('wrap').innerHTML=h;
  document.getElementById('navbarInner').innerHTML='';
  var go=function(i){ ts.idx=i; ts.maxReached=Math.max(ts.maxReached,i); renderSlide(); window.scrollTo({top:0,behavior:'smooth'}); };
  document.getElementById('btnGoSkipped').addEventListener('click',function(){ go(list[0]); });
  document.querySelectorAll('.skip-go').forEach(function(b){ b.addEventListener('click',function(){ go(parseInt(b.dataset.i,10)); }); });
  document.getElementById('btnSubmitAnyway').addEventListener('click',function(){ ts.submitOK=true; renderFinished(); ts.submitOK=false; });
  saveState();
}
var _rfSkip = renderFinished;
renderFinished = function(){
  var ts=state.tabs[activeTab];
  if(MODE==='quiz' && !ts.submitOK && skippedList(ts).length){ renderSkipGate(ts); return; }
  _rfSkip();
  if(MODE==='learning'){
    var list=skippedList(ts);
    if(list.length){
      var card=document.querySelector('.done-card');
      if(card){ var d=document.createElement('div'); d.className='skip-btns';
        d.innerHTML='<button class="btn btn-primary" id="btnGoSkipped">Attempt skipped questions ('+list.length+')</button>';
        card.appendChild(d);
        document.getElementById('btnGoSkipped').addEventListener('click',function(){ ts.idx=list[0]; ts.recorded=false; renderSlide(); window.scrollTo({top:0,behavior:'smooth'}); }); }
    }
  }
};


/* ================= approx answers (physics: within 1%) ================= */
var _amTools = answerMatches;
answerMatches = function(input,answer,accept,expr){
  if(expr==='approx'){
    var n1=parseNum(input); if(n1===null) return false;
    return [answer].concat(accept||[]).some(function(a){ var n2=parseNum(a); if(n2===null) return false; return Math.abs(n1-n2) <= Math.max(0.011*Math.abs(n2), 1e-9); });
  }
  return _amTools(input,answer,accept,expr);
};

/* ================= palette: every question already reached can be opened ================= */
statusOf = function(tabId,i){
  var ts=state.tabs[tabId];
  if(i>ts.maxReached) return 'locked';
  if(i===ts.idx) return 'current';
  var s=ts.items[i].status;
  if(s==='unanswered') return 'skipped';
  return s;
};

/* ================= on-screen keyboard ================= */
var KB={on:true, page:'num', target:null};
try{ var kbp=localStorage.getItem('sopaan-kb-pref'); if(kbp==='off') KB.on=false; }catch(e){}
function kbSave(){ try{ localStorage.setItem('sopaan-kb-pref', KB.on?'on':'off'); }catch(e){} }
var KEYS_NUM=[['7','8','9','÷','(',')'],['4','5','6','×','^','²'],['1','2','3','−','x','π'],['0','.','/','+','t','°'],['abc','←','→','⌫','Clear','Done']];
var KEYS_ABC=[['q','w','e','r','t','y','u','i','o','p'],['a','s','d','f','g','h','j','k','l','-'],['z','x','c','v','b','n','m',',',':','/'],['123','space','←','→','⌫','Done']];
function kbBuild(){
  var el=document.getElementById('vkb'); if(!el){ el=document.createElement('div'); el.id='vkb'; el.className='vkb'; document.body.appendChild(el);
    el.addEventListener('pointerdown',function(e){ var b=e.target.closest('button[data-k]'); e.preventDefault(); if(b) kbPress(b.dataset.k); });
    el.addEventListener('mousedown',function(e){ e.preventDefault(); }); }
  var rows=KB.page==='num'?KEYS_NUM:KEYS_ABC;
  el.innerHTML='<div class="vkb-top"><span>⌨️ Keyboard</span><button data-k="device" class="vkb-link">Use device keyboard</button></div>'+
    rows.map(function(r){ return '<div class="vkb-row">'+r.map(function(k){
      var cls='vkb-k'+(/^(abc|123|Done|Clear|⌫|←|→|space)$/.test(k)?' fn':'')+(k==='Done'?' done':'');
      return '<button type="button" class="'+cls+'" data-k="'+k+'">'+(k==='space'?'space':k)+'</button>'; }).join('')+'</div>'; }).join('');
  return el;
}
function kbShow(inp){ KB.target=inp; if(!KB.on) return; var cp=document.getElementById('calcPanel'); if(cp&&cp.classList.contains('show')) return; var el=kbBuild(); var nb=document.querySelector('.navbar'); el.style.bottom=(nb?nb.getBoundingClientRect().height:0)+'px'; el.classList.add('show'); document.body.classList.add('kb-open'); setTimeout(function(){ var r=inp.getBoundingClientRect(), top=el.getBoundingClientRect().top; if(r.bottom>top-12) window.scrollBy({top:r.bottom-top+60,behavior:'smooth'}); else if(r.top<60) window.scrollBy({top:r.top-80,behavior:'smooth'}); },30); }
function kbHide(){ var el=document.getElementById('vkb'); if(el) el.classList.remove('show'); document.body.classList.remove('kb-open'); }
function kbInsert(s){
  var t=KB.target; if(!t||t.disabled) return;
  var a=t.selectionStart==null?t.value.length:t.selectionStart, b=t.selectionEnd==null?a:t.selectionEnd;
  t.value=t.value.slice(0,a)+s+t.value.slice(b); var p=a+s.length; try{ t.setSelectionRange(p,p); }catch(e){}
  t.dispatchEvent(new Event('input',{bubbles:true}));
}
function kbPress(k){
  var t=KB.target; if(k==='device'){ KB.on=false; kbSave(); kbHide(); document.querySelectorAll('.blank-input').forEach(function(i){ i.removeAttribute('inputmode'); }); if(t){ t.blur(); setTimeout(function(){ t.focus(); },50); } showToast('Device keyboard on. Tap ⌨️ on any blank to bring the on-screen keyboard back.'); return; }
  if(k==='Done'){ kbHide(); if(t) t.blur(); return; }
  if(k==='abc'||k==='123'){ KB.page=(k==='abc')?'abc':'num'; kbBuild(); return; }
  if(!t) return;
  if(k==='⌫'){ var a=t.selectionStart, b=t.selectionEnd; if(a===b&&a>0){ t.value=t.value.slice(0,a-1)+t.value.slice(b); try{t.setSelectionRange(a-1,a-1);}catch(e){} } else { t.value=t.value.slice(0,a)+t.value.slice(b); try{t.setSelectionRange(a,a);}catch(e){} } t.dispatchEvent(new Event('input',{bubbles:true})); return; }
  if(k==='Clear'){ t.value=''; t.dispatchEvent(new Event('input',{bubbles:true})); return; }
  if(k==='←'||k==='→'){ var p=(t.selectionStart||0)+(k==='←'?-1:1); p=Math.max(0,Math.min(t.value.length,p)); try{t.setSelectionRange(p,p);}catch(e){} return; }
  var map={'−':'-','space':' '}; kbInsert(map[k]!==undefined?map[k]:k);
}
function kbWire(){
  document.querySelectorAll('.blank-input').forEach(function(inp){
    if(inp.dataset.kb) return; inp.dataset.kb='1';
    if(KB.on) inp.setAttribute('inputmode','none');
    inp.addEventListener('focus',function(){ kbShow(inp); });
    var btn=document.createElement('button'); btn.type='button'; btn.className='kb-toggle'; btn.title='On-screen keyboard'; btn.textContent='⌨️'; btn.tabIndex=-1;
    btn.addEventListener('mousedown',function(e){ e.preventDefault(); });
    btn.addEventListener('click',function(){ KB.on=true; kbSave(); document.querySelectorAll('.blank-input').forEach(function(i){ i.setAttribute('inputmode','none'); }); inp.focus(); kbShow(inp); });
    if(!inp.disabled) inp.insertAdjacentElement('afterend',btn);
  });
}
document.addEventListener('focusout',function(e){ setTimeout(function(){ var a=document.activeElement; if(!a||!a.classList||!a.classList.contains('blank-input')){ if(!document.querySelector('#vkb:hover')) kbHide(); } },120); });

/* ================= calculator ================= */
var CALC={expr:'', ans:0};
function calcEval(src){
  var s=String(src).replace(/×/g,'*').replace(/÷/g,'/').replace(/−/g,'-').replace(/π/g,'(PI)').replace(/Ans/g,'('+CALC.ans+')').replace(/\^/g,'**').replace(/√\(/g,'sqrt(').replace(/²/g,'**2').replace(/E/g,'*10**');
  s=s.replace(/(^|[(*\/+\-,])-/g,'$1(-1)*');
  if(/[^0-9+\-*/().,a-z A-Z]/.test(s)) throw 0;
  var ok=s.replace(/sin|cos|tan|asin|acos|atan|sqrt|log|ln|PI|abs/g,''); if(/[a-zA-Z]/.test(ok)) throw 0;
  var f=new Function('sin','cos','tan','asin','acos','atan','sqrt','log','ln','PI','abs','return ('+s+');');
  var d=Math.PI/180;
  var v=f(function(x){return Math.sin(x*d);},function(x){return Math.cos(x*d);},function(x){return Math.tan(x*d);},
    function(x){return Math.asin(x)/d;},function(x){return Math.acos(x)/d;},function(x){return Math.atan(x)/d;},Math.sqrt,Math.log10,Math.log,Math.PI,Math.abs);
  if(typeof v!=='number'||!isFinite(v)) throw 0; return v;
}
function fmtNum(v){ if(Math.abs(v)>=1e10||(Math.abs(v)<1e-6&&v!==0)) return v.toExponential(6).replace(/\.?0+e/,'e'); return String(parseFloat(v.toPrecision(10))); }
var CKEYS=[['sin(','cos(','tan(','√(','^','²'],['asin(','acos(','atan(','(',')','π'],['7','8','9','÷','⌫','AC'],['4','5','6','×','E','Ans'],['1','2','3','−','(−)','Insert'],['0','.','=','+']];
function openCalc(){
  var p=document.getElementById('calcPanel');
  if(!p){ p=document.createElement('div'); p.id='calcPanel'; p.className='tool-panel calc';
    p.innerHTML='<div class="tp-head"><b>🧮 Calculator</b><span class="tp-note">degrees · tap a blank, then Insert</span><button class="tp-x" data-c="close">✕</button></div>'+
      '<div class="calc-disp"><div class="calc-expr" id="calcExpr"></div><div class="calc-res" id="calcRes">0</div></div>'+
      '<div class="calc-keys">'+CKEYS.map(function(r){ return r.map(function(k){ return '<button type="button" data-c="'+k+'" class="'+(k==='='?'eq':(/^(AC|⌫|Insert)$/.test(k)?'fn':''))+'">'+({'sin(':'sin','cos(':'cos','tan(':'tan','asin(':'sin⁻¹','acos(':'cos⁻¹','atan(':'tan⁻¹','√(':'√'}[k]||k)+'</button>'; }).join(''); }).join('')+'</div>';
    document.body.appendChild(p);
    p.addEventListener('mousedown',function(e){ if(e.target.closest('button')) e.preventDefault(); });
    p.addEventListener('click',function(e){ var b=e.target.closest('button[data-c]'); if(!b) return; calcKey(b.dataset.c); });
  }
  kbHide(); var nb=document.querySelector('.navbar'); p.style.bottom=((nb?nb.getBoundingClientRect().height:0)+8)+'px'; p.classList.add('show'); document.body.classList.add('calc-open'); calcShow();
}
function calcShow(res){ document.getElementById('calcExpr').textContent=CALC.expr||' '; if(res!==undefined) document.getElementById('calcRes').textContent=res; }
function calcKey(k){
  if(k==='close'){ document.getElementById('calcPanel').classList.remove('show'); document.body.classList.remove('calc-open'); return; }
  if(k==='AC'){ CALC.expr=''; calcShow('0'); return; }
  if(k==='⌫'){ CALC.expr=CALC.expr.replace(/(asin\(|acos\(|atan\(|sin\(|cos\(|tan\(|√\(|Ans|.)$/,''); calcShow(); return; }
  if(k==='='){ try{ var v=calcEval(CALC.expr); CALC.ans=v; calcShow(fmtNum(v)); }catch(e){ calcShow('Error'); } return; }
  if(k==='(−)'){ CALC.expr+='−'; calcShow(); return; }
  if(k==='Insert'){ var r=document.getElementById('calcRes').textContent; if(KB.target && !KB.target.disabled && r!=='Error'){ KB.target.value=r; KB.target.dispatchEvent(new Event('input',{bubbles:true})); showToast('Inserted '+r+' into the blank.'); } else showToast('Tap a blank first, then press Insert.'); return; }
  CALC.expr+=k; calcShow();
}

/* ================= Desmos ================= */
var DESMOS_KEY='dcb31709b452b1cf9dc26972add0fda6', desmosCalc=null, desmosLoading=false;
function openDesmos(exprs){
  var p=document.getElementById('desmosPanel');
  if(!p){ p=document.createElement('div'); p.id='desmosPanel'; p.className='tool-panel desmos';
    p.innerHTML='<div class="tp-head"><b>📈 Desmos graphing calculator</b><button class="tp-x" id="desmosReset">Reset graph</button><button class="tp-x" id="desmosClose">✕</button></div><div id="desmosBox"><div class="desmos-msg">Loading Desmos…</div></div>';
    document.body.appendChild(p);
    document.getElementById('desmosClose').addEventListener('click',function(){ p.classList.remove('show'); });
    document.getElementById('desmosReset').addEventListener('click',function(){ if(desmosCalc) desmosSet(p._exprs||[]); });
  }
  p._exprs=exprs||[]; p.classList.add('show');
  if(window.Desmos){ desmosInit(); desmosSet(p._exprs); return; }
  if(desmosLoading) return; desmosLoading=true;
  var sc=document.createElement('script'); sc.src='https://www.desmos.com/api/v1.9/calculator.js?apiKey='+DESMOS_KEY;
  sc.onload=function(){ desmosInit(); desmosSet(p._exprs); };
  sc.onerror=function(){ desmosLoading=false; document.getElementById('desmosBox').innerHTML='<div class="desmos-msg">Desmos needs an internet connection. <a href="https://www.desmos.com/calculator" target="_blank" rel="noopener">Open Desmos in a new tab</a>.</div>'; };
  document.head.appendChild(sc);
}
function desmosInit(){ if(desmosCalc) return; var box=document.getElementById('desmosBox'); box.innerHTML=''; desmosCalc=Desmos.GraphingCalculator(box,{expressionsCollapsed:false,settingsMenu:false,border:false,degreeMode:true}); }
function desmosSet(exprs){ if(!desmosCalc) return; desmosCalc.setBlank(); (exprs||[]).forEach(function(e,i){ if(typeof e==='string') desmosCalc.setExpression({id:'e'+i,latex:e}); else desmosCalc.setExpression(Object.assign({id:'e'+i},e)); }); }

/* ================= toolbar on each question ================= */
var _rsTools = renderSlide;
renderSlide = function(){
  _rsTools();
  kbHide();
  if(activeTab==='theory'||activeTab==='report') return;
  var ts=state.tabs[activeTab]; if(!ts) return;
  var slide=SLIDES[activeTab][ts.idx], card=document.querySelector('#wrap .qcard');
  if(card && slide && slide.tools && slide.tools.length && !card.querySelector('.tool-bar')){
    var bar=document.createElement('div'); bar.className='tool-bar';
    bar.innerHTML=(slide.tools.indexOf('calc')>=0?'<button type="button" class="tool-btn" data-t="calc">🧮 Calculator</button>':'')+
                  (slide.tools.indexOf('desmos')>=0?'<button type="button" class="tool-btn" data-t="desmos">📈 Desmos graph</button>':'');
    card.insertBefore(bar, card.firstChild);
    bar.addEventListener('click',function(e){ var b=e.target.closest('[data-t]'); if(!b) return; if(b.dataset.t==='calc') openCalc(); else openDesmos(slide.desmos||[]); });
  }
  kbWire();
};

renderLogin();
})();
</script>
</body>
</html>
