<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="utf-8">
<meta name="viewport" content="width=device-width, initial-scale=1, viewport-fit=cover">
<title>Sopaan · Kinematics</title>
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
  <div class="chapter-eyebrow">AP Physics 1 · Chapter 1</div>
  <div class="chapter-title">Kinematics</div>
  <div class="chapter-sub">Theory Notes · Practice by Learning Objective · Tests A–D</div><div class="chapter-credit">Organised by AP Physics 1 CED learning objectives · Unit 1</div>
  <div class="chapter-progress">
    <div class="cp-track"><div class="cp-fill" id="cpFill"></div></div>
    <div class="cp-label" id="cpLabel">0% complete</div>
  </div>
  <div class="who-row"><button class="mode-pill" id="modePill" hidden>Choose a mode</button><span class="who" id="whoBar" hidden></span></div>
</header>

<nav class="tabbar"><div class="tabbar-inner" id="tabbar"></div></nav>
<div class="sec-sub" id="secSub"></div><div class="slide-progress"><div class="sp-track"><div class="sp-fill" id="spFill"></div></div><div class="sp-label" id="spLabel">Question 1 of 49</div></div>
<div class="wrap" id="wrap"></div>
<footer class="brandfoot">Brain &amp; Mind Academy · Sopaan Practice Series · AP Physics 1 · Chapter 1<br>Organised by the topics and learning objectives of the AP Physics 1 Course and Exam Description (College Board, 2024), Unit 1. Theory notes, questions, tests and worked solutions are written by Brain &amp; Mind Academy; no workbook or College Board questions are reproduced.</footer>

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
var THEORY = "<div class=\"hub\"><div class=\"hub-card\"><h3>📖 Theory notes</h3><p>Notes for each CED topic, with the learning objectives, equations, graphs and worked examples.</p><div class=\"hub-btns\"><button class=\"hub-btn\" data-jump=\"n11\">Topic 1.1</button><button class=\"hub-btn\" data-jump=\"n12\">Topic 1.2</button><button class=\"hub-btn\" data-jump=\"n13\">Topic 1.3</button><button class=\"hub-btn\" data-jump=\"n14\">Topic 1.4</button><button class=\"hub-btn\" data-jump=\"n15\">Topic 1.5</button></div></div><div class=\"hub-card\"><h3>🎯 Practice by learning objective</h3><p>One practice sheet per learning objective: multiple choice first, then step-by-step blanks. 🧮 and 📈 appear where a calculator or graph helps.</p><div class=\"hub-btns\"><div class=\"hub-grp\">Topic 1.1 · Scalars and Vectors in One Dimension</div><button class=\"hub-btn\" data-go=\"s1\">1.1.A · Scalars and vectors</button><button class=\"hub-btn\" data-go=\"s2\">1.1.B · Vector addition in one dimension</button><div class=\"hub-grp\">Topic 1.2 · Displacement, Velocity, and Acceleration</div><button class=\"hub-btn\" data-go=\"s3\">1.2.A · Change in position</button><button class=\"hub-btn\" data-go=\"s4\">1.2.B · Average velocity and acceleration</button><div class=\"hub-grp\">Topic 1.3 · Representing Motion</div><button class=\"hub-btn\" data-go=\"s5\">1.3.A (i) · Motion graphs</button><button class=\"hub-btn\" data-go=\"s6\">1.3.A (ii) · Kinematic equations</button><button class=\"hub-btn\" data-go=\"s7\">1.3.A (iii) · Free fall</button><div class=\"hub-grp\">Topic 1.4 · Reference Frames and Relative Motion</div><button class=\"hub-btn\" data-go=\"s8\">1.4.A · Reference frames</button><button class=\"hub-btn\" data-go=\"s9\">1.4.B · Relative motion</button><div class=\"hub-grp\">Topic 1.5 · Vectors and Motion in Two Dimensions</div><button class=\"hub-btn\" data-go=\"s10\">1.5.A · Vector components</button><button class=\"hub-btn\" data-go=\"s11\">1.5.B · Motion in two dimensions</button></div></div><div class=\"hub-card\"><h3>📝 Unit test</h3><p>Four tests, one per category. Take them in Quiz mode, then open the report for your pie charts.</p><div class=\"hub-btns\"><button class=\"hub-btn\" data-go=\"s12\">Test A · Knowing and understanding</button><button class=\"hub-btn\" data-go=\"s13\">Test B · Investigating patterns</button><button class=\"hub-btn\" data-go=\"s14\">Test C · Communicating</button><button class=\"hub-btn\" data-go=\"s15\">Test D · Applying physics in real-life contexts</button><button class=\"hub-btn primary\" data-go=\"report\">📊 View my report</button></div></div></div><style>.hub-grp{width:100%;font:700 12px 'Source Sans 3',sans-serif;color:var(--ink-soft);text-transform:uppercase;letter-spacing:.05em;margin-top:6px;}</style><section class=\"note\" id=\"nintro\"><h2>About this unit</h2><p>Unit 1 of AP Physics 1 is <b>kinematics</b>: describing motion with position, velocity, acceleration and time. The practice tabs follow the College Board course framework, one tab for each learning objective (1.3.A is large, so it has three tabs).</p><div class=\"tscroll\"><table class=\"ttab\"><tr><th>Topic</th><th>Learning objective</th><th>Practice tab</th></tr><tr><td>1.1</td><td><b>1.1.A</b> Describe a scalar or vector quantity using magnitude and direction, as appropriate.</td><td>1.1.A</td></tr><tr><td>1.1</td><td><b>1.1.B</b> Describe a vector sum in one dimension.</td><td>1.1.B</td></tr><tr><td>1.2</td><td><b>1.2.A</b> Describe a change in an object's position.</td><td>1.2.A</td></tr><tr><td>1.2</td><td><b>1.2.B</b> Describe the average velocity and acceleration of an object.</td><td>1.2.B</td></tr><tr><td>1.3</td><td><b>1.3.A</b> Describe the position, velocity and acceleration of an object using graphs of its motion.</td><td>1.3.A (i)</td></tr><tr><td>1.3</td><td><b>1.3.A</b> Describe the position, velocity and acceleration of an object using the equations for constant acceleration.</td><td>1.3.A (ii)</td></tr><tr><td>1.3</td><td><b>1.3.A</b> Describe the motion of an object in free fall near Earth's surface (g ≈ 10 m/s² downward).</td><td>1.3.A (iii)</td></tr><tr><td>1.4</td><td><b>1.4.A</b> Describe the reference frame of a given observer.</td><td>1.4.A</td></tr><tr><td>1.4</td><td><b>1.4.B</b> Describe the motion of objects as measured by observers in different inertial reference frames.</td><td>1.4.B</td></tr><tr><td>1.5</td><td><b>1.5.A</b> Describe the perpendicular components of a vector.</td><td>1.5.A</td></tr><tr><td>1.5</td><td><b>1.5.B</b> Describe the motion of an object moving in two dimensions (projectiles).</td><td>1.5.B</td></tr></table></div><div class=\"tscroll\"><table class=\"ttab\"><tr><th>Equation (constant a, one dimension)</th><th>Missing</th></tr><tr><td class=\"mono\">v<sub>x</sub>&nbsp;=&nbsp;v<sub>x0</sub> + a<sub>x</sub>t</td><td>x</td></tr><tr><td class=\"mono\">x&nbsp;=&nbsp;x₀ + v<sub>x0</sub>t + ½a<sub>x</sub>t²</td><td>v<sub>x</sub></td></tr><tr><td class=\"mono\">v<sub>x</sub>²&nbsp;=&nbsp;v<sub>x0</sub>² + 2a<sub>x</sub>(x − x₀)</td><td>t</td></tr></table></div><p>Use <b>g ≈ 10 m/s²</b> downward and ignore air resistance unless told otherwise. Rounded answers are accepted within about 1%.</p><div class=\"tscroll\"><table class=\"ttab\"><tr><th>Test</th><th>Category</th><th>What it checks</th></tr><tr><td>A</td><td>Knowing and understanding</td><td>Definitions, equations and graphs used correctly.</td></tr><tr><td>B</td><td>Investigating patterns</td><td>Relationships in data tables and graphs; predicting.</td></tr><tr><td>C</td><td>Communicating</td><td>Units, signs, significant figures, representations, spotting errors.</td></tr><tr><td>D</td><td>Applying physics in real-life contexts</td><td>Road safety, sport and rescue problems; judging reasonableness.</td></tr></table></div><p><b>Tools:</b> every blank opens an on-screen keyboard (⌨️ brings it back). 🧮 opens a scientific calculator (degrees; Insert puts the result in the blank). 📈 opens a Desmos graph set up for the question.</p></section><section class=\"note\" id=\"n11\"><h2>Topic 1.1 · Scalars and Vectors in One Dimension</h2><p class=\"lt\"><b>Learning objectives</b></p><ul class=\"lt\"><li><b>1.1.A</b> Describe a scalar or vector quantity using magnitude and direction, as appropriate.</li><li><b>1.1.B</b> Describe a vector sum in one dimension.</li></ul><p>A <b>scalar</b> has magnitude only: distance, speed, time, mass. A <b>vector</b> has magnitude and direction: position, displacement, velocity, acceleration. A vector is drawn as an arrow whose length is proportional to its magnitude.</p><p>In one dimension, choose a positive direction; the <b>sign</b> of a component gives the direction. v<sub>x</sub> = −4 m/s means 4 m/s in the negative direction. The magnitude is always positive.</p><h4>Adding vectors in one dimension</h4><p>Add the components with their signs. Opposite directions have opposite signs, so they partly cancel.</p><div class=\"ex\"><div class=\"exh\">Worked example · 1D vector sum</div><div class=\"exl\">A robot moves +12 m, then −7 m, then +4 m.<br>Displacement = 12 − 7 + 4 = <b>+9 m</b>; distance = 12 + 7 + 4 = 23 m.</div></div><div class=\"keybox\"><b>Magnitude vs component.</b> −9 m and +9 m have the same magnitude (9 m) but opposite directions. “Speed” is the magnitude of velocity, so it is never negative.</div><div class=\"hub-btns\" style=\"margin-top:12px\"><button class=\"hub-btn primary\" data-go=\"s1\">Practise 1.1.A →</button><button class=\"hub-btn primary\" data-go=\"s2\">Practise 1.1.B →</button></div></section><section class=\"note\" id=\"n12\"><h2>Topic 1.2 · Displacement, Velocity, and Acceleration</h2><p class=\"lt\"><b>Learning objectives</b></p><ul class=\"lt\"><li><b>1.2.A</b> Describe a change in an object's position.</li><li><b>1.2.B</b> Describe the average velocity and acceleration of an object.</li></ul><p>In the <b>object model</b> we treat a moving thing as a point, ignoring its size and shape. Its <b>displacement</b> is the change in position: Δx = x<sub>f</sub> − x<sub>i</sub>.</p><div class=\"tscroll\"><table class=\"ttab\"><tr><th>Quantity</th><th>Definition</th></tr><tr><td>average velocity</td><td class=\"mono\">v<sub>avg</sub>&nbsp;=&nbsp;Δx ÷ Δt</td></tr><tr><td>average speed</td><td class=\"mono\">distance ÷ Δt</td></tr><tr><td>average acceleration</td><td class=\"mono\">a<sub>avg</sub>&nbsp;=&nbsp;Δv ÷ Δt</td></tr></table></div><p>An object accelerates whenever its velocity changes in <b>magnitude or direction</b>. Over a very small time interval the average values become the <b>instantaneous</b> velocity and acceleration.</p><div class=\"ex\"><div class=\"exh\">Worked example 1 · Distance vs displacement</div><div class=\"exl\">Rahul walks 120 m east in 100 s, then 50 m west in 40 s.<br>Distance 170 m; displacement 70 m east.<br>Average speed ≈ 1.21 m/s; average velocity = 70 ÷ 140 = <b>0.50 m/s east</b>.</div></div><div class=\"ex\"><div class=\"exh\">Worked example 2 · Average acceleration</div><div class=\"exl\">A car goes from 18 m/s to 6 m/s (same direction) in 4.0 s.<br>a = (6 − 18) ÷ 4.0 = <b>−3 m/s²</b>: the acceleration points opposite to the motion, so the car slows.</div></div><div class=\"keybox\"><b>Back where you started?</b> Displacement and average velocity are zero, however far you went. 72 km/h = 20 m/s (divide by 3.6).</div><div class=\"hub-btns\" style=\"margin-top:12px\"><button class=\"hub-btn primary\" data-go=\"s3\">Practise 1.2.A →</button><button class=\"hub-btn primary\" data-go=\"s4\">Practise 1.2.B →</button></div></section><section class=\"note\" id=\"n13\"><h2>Topic 1.3 · Representing Motion</h2><p class=\"lt\"><b>Learning objectives</b></p><ul class=\"lt\"><li><b>1.3.A</b> Describe the position, velocity and acceleration of an object using graphs of its motion.</li></ul><p>Motion can be shown with motion diagrams, graphs, equations and words. Each must tell the same story.</p><div class=\"tscroll\"><table class=\"ttab\"><tr><th>Graph</th><th>Slope</th><th>Area under it</th></tr><tr><td>x–t</td><td>velocity (tangent slope = instantaneous v)</td><td>—</td></tr><tr><td>v–t</td><td>acceleration</td><td>displacement</td></tr><tr><td>a–t</td><td>—</td><td>change in velocity</td></tr></table></div><svg class=\"figsvg\" viewBox=\"0 0 320 230\" role=\"img\"><defs><marker id=\"ah\" viewBox=\"0 0 10 10\" refX=\"9\" refY=\"5\" markerWidth=\"7\" markerHeight=\"7\" orient=\"auto\"><path d=\"M0,1 L10,5 L0,9 z\" class=\"ahd\"/></marker><marker id=\"ahs\" viewBox=\"0 0 10 10\" refX=\"1\" refY=\"5\" markerWidth=\"7\" markerHeight=\"7\" orient=\"auto\"><path d=\"M10,1 L0,5 L10,9 z\" class=\"ahd\"/></marker></defs><line style=\"stroke:var(--rule)\" x1=\"46.0\" y1=\"196\" x2=\"46.0\" y2=\"18\"/><text class=\"po\" x=\"46.0\" y=\"209.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">0</text><line style=\"stroke:var(--rule)\" x1=\"67.2\" y1=\"196\" x2=\"67.2\" y2=\"18\"/><text class=\"po\" x=\"67.2\" y=\"209.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">1</text><line style=\"stroke:var(--rule)\" x1=\"88.3\" y1=\"196\" x2=\"88.3\" y2=\"18\"/><text class=\"po\" x=\"88.3\" y=\"209.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">2</text><line style=\"stroke:var(--rule)\" x1=\"109.5\" y1=\"196\" x2=\"109.5\" y2=\"18\"/><text class=\"po\" x=\"109.5\" y=\"209.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">3</text><line style=\"stroke:var(--rule)\" x1=\"130.7\" y1=\"196\" x2=\"130.7\" y2=\"18\"/><text class=\"po\" x=\"130.7\" y=\"209.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">4</text><line style=\"stroke:var(--rule)\" x1=\"151.8\" y1=\"196\" x2=\"151.8\" y2=\"18\"/><text class=\"po\" x=\"151.8\" y=\"209.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">5</text><line style=\"stroke:var(--rule)\" x1=\"173.0\" y1=\"196\" x2=\"173.0\" y2=\"18\"/><text class=\"po\" x=\"173.0\" y=\"209.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">6</text><line style=\"stroke:var(--rule)\" x1=\"194.2\" y1=\"196\" x2=\"194.2\" y2=\"18\"/><text class=\"po\" x=\"194.2\" y=\"209.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">7</text><line style=\"stroke:var(--rule)\" x1=\"215.3\" y1=\"196\" x2=\"215.3\" y2=\"18\"/><text class=\"po\" x=\"215.3\" y=\"209.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">8</text><line style=\"stroke:var(--rule)\" x1=\"236.5\" y1=\"196\" x2=\"236.5\" y2=\"18\"/><text class=\"po\" x=\"236.5\" y=\"209.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">9</text><line style=\"stroke:var(--rule)\" x1=\"257.7\" y1=\"196\" x2=\"257.7\" y2=\"18\"/><text class=\"po\" x=\"257.7\" y=\"209.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">10</text><line style=\"stroke:var(--rule)\" x1=\"278.8\" y1=\"196\" x2=\"278.8\" y2=\"18\"/><text class=\"po\" x=\"278.8\" y=\"209.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">11</text><line style=\"stroke:var(--rule)\" x1=\"300.0\" y1=\"196\" x2=\"300.0\" y2=\"18\"/><text class=\"po\" x=\"300.0\" y=\"209.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">12</text><line style=\"stroke:var(--rule)\" x1=\"46\" y1=\"196.0\" x2=\"300\" y2=\"196.0\"/><text class=\"po\" x=\"40.0\" y=\"196.0\" text-anchor=\"end\" dominant-baseline=\"middle\">0</text><line style=\"stroke:var(--rule)\" x1=\"46\" y1=\"160.4\" x2=\"300\" y2=\"160.4\"/><text class=\"po\" x=\"40.0\" y=\"160.4\" text-anchor=\"end\" dominant-baseline=\"middle\">2</text><line style=\"stroke:var(--rule)\" x1=\"46\" y1=\"124.8\" x2=\"300\" y2=\"124.8\"/><text class=\"po\" x=\"40.0\" y=\"124.8\" text-anchor=\"end\" dominant-baseline=\"middle\">4</text><line style=\"stroke:var(--rule)\" x1=\"46\" y1=\"89.2\" x2=\"300\" y2=\"89.2\"/><text class=\"po\" x=\"40.0\" y=\"89.2\" text-anchor=\"end\" dominant-baseline=\"middle\">6</text><line style=\"stroke:var(--rule)\" x1=\"46\" y1=\"53.6\" x2=\"300\" y2=\"53.6\"/><text class=\"po\" x=\"40.0\" y=\"53.6\" text-anchor=\"end\" dominant-baseline=\"middle\">8</text><line style=\"stroke:var(--rule)\" x1=\"46\" y1=\"18.0\" x2=\"300\" y2=\"18.0\"/><text class=\"po\" x=\"40.0\" y=\"18.0\" text-anchor=\"end\" dominant-baseline=\"middle\">10</text><line class=\"ln\" x1=\"46.0\" y1=\"196.0\" x2=\"308.0\" y2=\"196.0\" marker-end=\"url(#ah)\"/><line class=\"ln\" x1=\"46.0\" y1=\"196.0\" x2=\"46.0\" y2=\"10.0\" marker-end=\"url(#ah)\"/><text class=\"lb\" x=\"300.0\" y=\"188.0\" text-anchor=\"end\" dominant-baseline=\"middle\">t (s)</text><text class=\"lb\" x=\"52.0\" y=\"12.0\" text-anchor=\"start\" dominant-baseline=\"middle\">v (m/s)</text><polyline fill=\"none\" style=\"stroke:var(--danger);stroke-width:2.2\" points=\"46.0,196.0 130.7,53.6 257.7,53.6 300.0,196.0\"/><circle cx=\"46.0\" cy=\"196.0\" r=\"3\" style=\"fill:var(--danger)\"/><circle cx=\"130.7\" cy=\"53.6\" r=\"3\" style=\"fill:var(--danger)\"/><circle cx=\"257.7\" cy=\"53.6\" r=\"3\" style=\"fill:var(--danger)\"/><circle cx=\"300.0\" cy=\"196.0\" r=\"3\" style=\"fill:var(--danger)\"/></svg><div class=\"ex\"><div class=\"exh\">Worked example 1 · v–t graph</div><div class=\"exl\">0–4 s: slope 8 ÷ 4 = 2 m/s². Area = 16 + 48 + 8 = <b>72 m</b>. Last 2 s: −4 m/s².</div></div><svg class=\"figsvg\" viewBox=\"0 0 320 230\" role=\"img\"><defs><marker id=\"ah\" viewBox=\"0 0 10 10\" refX=\"9\" refY=\"5\" markerWidth=\"7\" markerHeight=\"7\" orient=\"auto\"><path d=\"M0,1 L10,5 L0,9 z\" class=\"ahd\"/></marker><marker id=\"ahs\" viewBox=\"0 0 10 10\" refX=\"1\" refY=\"5\" markerWidth=\"7\" markerHeight=\"7\" orient=\"auto\"><path d=\"M10,1 L0,5 L10,9 z\" class=\"ahd\"/></marker></defs><line style=\"stroke:var(--rule)\" x1=\"46.0\" y1=\"196\" x2=\"46.0\" y2=\"18\"/><text class=\"po\" x=\"46.0\" y=\"209.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">0</text><line style=\"stroke:var(--rule)\" x1=\"88.3\" y1=\"196\" x2=\"88.3\" y2=\"18\"/><text class=\"po\" x=\"88.3\" y=\"209.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">1</text><line style=\"stroke:var(--rule)\" x1=\"130.7\" y1=\"196\" x2=\"130.7\" y2=\"18\"/><text class=\"po\" x=\"130.7\" y=\"209.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">2</text><line style=\"stroke:var(--rule)\" x1=\"173.0\" y1=\"196\" x2=\"173.0\" y2=\"18\"/><text class=\"po\" x=\"173.0\" y=\"209.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">3</text><line style=\"stroke:var(--rule)\" x1=\"215.3\" y1=\"196\" x2=\"215.3\" y2=\"18\"/><text class=\"po\" x=\"215.3\" y=\"209.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">4</text><line style=\"stroke:var(--rule)\" x1=\"257.7\" y1=\"196\" x2=\"257.7\" y2=\"18\"/><text class=\"po\" x=\"257.7\" y=\"209.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">5</text><line style=\"stroke:var(--rule)\" x1=\"300.0\" y1=\"196\" x2=\"300.0\" y2=\"18\"/><text class=\"po\" x=\"300.0\" y=\"209.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">6</text><line style=\"stroke:var(--rule)\" x1=\"46\" y1=\"196.0\" x2=\"300\" y2=\"196.0\"/><text class=\"po\" x=\"40.0\" y=\"196.0\" text-anchor=\"end\" dominant-baseline=\"middle\">0</text><line style=\"stroke:var(--rule)\" x1=\"46\" y1=\"151.5\" x2=\"300\" y2=\"151.5\"/><text class=\"po\" x=\"40.0\" y=\"151.5\" text-anchor=\"end\" dominant-baseline=\"middle\">2</text><line style=\"stroke:var(--rule)\" x1=\"46\" y1=\"107.0\" x2=\"300\" y2=\"107.0\"/><text class=\"po\" x=\"40.0\" y=\"107.0\" text-anchor=\"end\" dominant-baseline=\"middle\">4</text><line style=\"stroke:var(--rule)\" x1=\"46\" y1=\"62.5\" x2=\"300\" y2=\"62.5\"/><text class=\"po\" x=\"40.0\" y=\"62.5\" text-anchor=\"end\" dominant-baseline=\"middle\">6</text><line style=\"stroke:var(--rule)\" x1=\"46\" y1=\"18.0\" x2=\"300\" y2=\"18.0\"/><text class=\"po\" x=\"40.0\" y=\"18.0\" text-anchor=\"end\" dominant-baseline=\"middle\">8</text><line class=\"ln\" x1=\"46.0\" y1=\"196.0\" x2=\"308.0\" y2=\"196.0\" marker-end=\"url(#ah)\"/><line class=\"ln\" x1=\"46.0\" y1=\"196.0\" x2=\"46.0\" y2=\"10.0\" marker-end=\"url(#ah)\"/><text class=\"lb\" x=\"300.0\" y=\"188.0\" text-anchor=\"end\" dominant-baseline=\"middle\">t (s)</text><text class=\"lb\" x=\"52.0\" y=\"12.0\" text-anchor=\"start\" dominant-baseline=\"middle\">x (m)</text><polyline fill=\"none\" style=\"stroke:var(--danger);stroke-width:2.2\" points=\"46.0,196.0 130.7,62.5 215.3,62.5 300.0,196.0\"/><circle cx=\"46.0\" cy=\"196.0\" r=\"3\" style=\"fill:var(--danger)\"/><circle cx=\"130.7\" cy=\"62.5\" r=\"3\" style=\"fill:var(--danger)\"/><circle cx=\"215.3\" cy=\"62.5\" r=\"3\" style=\"fill:var(--danger)\"/><circle cx=\"300.0\" cy=\"196.0\" r=\"3\" style=\"fill:var(--danger)\"/></svg><div class=\"ex\"><div class=\"exh\">Worked example 2 · x–t graph</div><div class=\"exl\">0–2 s: +3 m/s; 2–4 s: at rest; 4–6 s: −3 m/s. Distance 12 m, displacement 0.</div></div><h4>Constant acceleration</h4><p>Use the three equations in the table at the top. List what you know, pick the equation without the unknown you do not need, substitute with signs.</p><div class=\"ex\"><div class=\"exh\">Worked example 3 · Braking</div><div class=\"exl\">30 m/s to rest at −5 m/s²: 0 = 900 − 10Δx, Δx = <b>90 m</b>. Doubling the speed makes the stopping distance 4 times as long.</div></div><h4>Free fall</h4><p>Near Earth, a freely falling object has a = g ≈ 10 m/s² <b>downward</b> all the time — going up, at the top and coming down — whatever its mass.</p><div class=\"ex\"><div class=\"exh\">Worked example 4 · Thrown up</div><div class=\"exl\">Up at 15 m/s: time to top 1.5 s, height 15² ÷ 20 = 11.25 m, back at launch height after 3.0 s.</div></div><div class=\"keybox\"><b>At the top of a throw v = 0 but a = 10 m/s² down.</b> From rest, distances fallen in successive seconds are 5, 15, 25 m (ratio 1 : 3 : 5).</div><div class=\"hub-btns\" style=\"margin-top:12px\"><button class=\"hub-btn primary\" data-go=\"s5\">Practise 1.3.A (i) →</button><button class=\"hub-btn primary\" data-go=\"s6\">Practise 1.3.A (ii) →</button><button class=\"hub-btn primary\" data-go=\"s7\">Practise 1.3.A (iii) →</button></div></section><section class=\"note\" id=\"n14\"><h2>Topic 1.4 · Reference Frames and Relative Motion</h2><p class=\"lt\"><b>Learning objectives</b></p><ul class=\"lt\"><li><b>1.4.A</b> Describe the reference frame of a given observer.</li><li><b>1.4.B</b> Describe the motion of objects as measured by observers in different inertial reference frames.</li></ul><p>A <b>reference frame</b> is the viewpoint (origin, axes and observer) from which motion is measured. The same object can be at rest in one frame and moving in another: a passenger sitting in a train is at rest relative to the train but moving relative to the platform.</p><p>For frames moving at constant velocity (inertial frames), velocities combine by vector addition: <span class=\"mono\">v<sub>object, ground</sub> = v<sub>object, train</sub> + v<sub>train, ground</sub></span>. All inertial observers measure the <b>same acceleration</b>.</p><div class=\"ex\"><div class=\"exh\">Worked example 1 · Walking in a train</div><div class=\"exl\">Train 20 m/s east; passenger walks 1.5 m/s east inside it.<br>Relative to the ground: 20 + 1.5 = <b>21.5 m/s east</b>. Walking towards the back: 18.5 m/s east.</div></div><div class=\"ex\"><div class=\"exh\">Worked example 2 · Rain on a moving car</div><div class=\"exl\">Rain falls vertically at 6 m/s; a car drives at 8 m/s.<br>In the car's frame the rain has 6 m/s down and 8 m/s backwards: √(6² + 8²) = <b>10 m/s</b>, slanting towards the car.</div></div><div class=\"keybox\"><b>Changing the origin changes positions but not displacements.</b> Changing the frame changes velocities (and positions), but never accelerations between inertial frames.</div><div class=\"hub-btns\" style=\"margin-top:12px\"><button class=\"hub-btn primary\" data-go=\"s8\">Practise 1.4.A →</button><button class=\"hub-btn primary\" data-go=\"s9\">Practise 1.4.B →</button></div></section><section class=\"note\" id=\"n15\"><h2>Topic 1.5 · Vectors and Motion in Two Dimensions</h2><p class=\"lt\"><b>Learning objectives</b></p><ul class=\"lt\"><li><b>1.5.A</b> Describe the perpendicular components of a vector.</li><li><b>1.5.B</b> Describe the motion of an object moving in two dimensions (projectiles).</li></ul><p>Any vector can be modelled as the sum of two perpendicular <b>components</b>. For magnitude v at angle θ to the x-axis: v<sub>x</sub> = v cos θ, v<sub>y</sub> = v sin θ; and v = √(v<sub>x</sub>² + v<sub>y</sub>²), θ = tan⁻¹(v<sub>y</sub> ÷ v<sub>x</sub>).</p><svg class=\"figsvg\" viewBox=\"0 0 260 170\" role=\"img\"><defs><marker id=\"ah\" viewBox=\"0 0 10 10\" refX=\"9\" refY=\"5\" markerWidth=\"7\" markerHeight=\"7\" orient=\"auto\"><path d=\"M0,1 L10,5 L0,9 z\" class=\"ahd\"/></marker><marker id=\"ahs\" viewBox=\"0 0 10 10\" refX=\"1\" refY=\"5\" markerWidth=\"7\" markerHeight=\"7\" orient=\"auto\"><path d=\"M10,1 L0,5 L10,9 z\" class=\"ahd\"/></marker></defs><line style=\"stroke:var(--accent-text);stroke-width:2.2\" x1=\"40.0\" y1=\"140.0\" x2=\"40.0\" y2=\"32.0\" marker-end=\"url(#ah)\"/><text class=\"lb\" x=\"14.0\" y=\"78.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">6 km N</text><line style=\"stroke:var(--success);stroke-width:2.2\" x1=\"40.0\" y1=\"32.0\" x2=\"184.0\" y2=\"32.0\" marker-end=\"url(#ah)\"/><text class=\"lb\" x=\"120.0\" y=\"24.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">8 km E</text><line style=\"stroke:var(--danger);stroke-width:2.2\" x1=\"40.0\" y1=\"140.0\" x2=\"184.0\" y2=\"32.0\" marker-end=\"url(#ah)\"/><text class=\"lb\" x=\"120.0\" y=\"78.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">R</text></svg><p>Two-dimensional motion is analysed as two <b>independent one-dimensional motions</b> sharing the same time. A projectile has a<sub>x</sub> = 0 (constant v<sub>x</sub>) and a<sub>y</sub> = −10 m/s².</p><svg class=\"figsvg\" viewBox=\"0 0 320 200\" role=\"img\"><defs><marker id=\"ah\" viewBox=\"0 0 10 10\" refX=\"9\" refY=\"5\" markerWidth=\"7\" markerHeight=\"7\" orient=\"auto\"><path d=\"M0,1 L10,5 L0,9 z\" class=\"ahd\"/></marker><marker id=\"ahs\" viewBox=\"0 0 10 10\" refX=\"1\" refY=\"5\" markerWidth=\"7\" markerHeight=\"7\" orient=\"auto\"><path d=\"M10,1 L0,5 L10,9 z\" class=\"ahd\"/></marker></defs><text class=\"lb\" x=\"160.0\" y=\"10.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">Horizontal launch from a 20 m cliff</text><line x1=\"4.0\" y1=\"178.0\" x2=\"316\" y2=\"178.0\" style=\"stroke:var(--ink);stroke-width:1.6\"/><rect x=\"4.0\" y=\"59.7\" width=\"20.0\" height=\"118.3\" style=\"fill:var(--gold-soft);stroke:var(--ink);stroke-width:1.2\"/><polyline points=\"24.0,59.7 27.6,59.7 31.3,59.8 34.9,60.0 38.5,60.2 42.1,60.5 45.8,60.8 49.4,61.3 53.0,61.8 56.6,62.3 60.3,63.0 63.9,63.6 67.5,64.4 71.1,65.2 74.8,66.1 78.4,67.1 82.0,68.1 85.7,69.2 89.3,70.3 92.9,71.5 96.5,72.8 100.2,74.2 103.8,75.6 107.4,77.1 111.0,78.6 114.7,80.2 118.3,81.9 121.9,83.6 125.5,85.4 129.2,87.3 132.8,89.2 136.4,91.3 140.1,93.3 143.7,95.5 147.3,97.7 150.9,99.9 154.6,102.3 158.2,104.7 161.8,107.1 165.4,109.7 169.1,112.3 172.7,114.9 176.3,117.6 179.9,120.4 183.6,123.3 187.2,126.2 190.8,129.2 194.5,132.3 198.1,135.4 201.7,138.6 205.3,141.8 209.0,145.2 212.6,148.5 216.2,152.0 219.8,155.5 223.5,159.1 227.1,162.7 230.7,166.5 234.3,170.2 238.0,174.1 241.6,178.0\" style=\"fill:none;stroke:var(--danger);stroke-width:2;stroke-dasharray:5 4\"/><circle cx=\"24.0\" cy=\"59.7\" r=\"4\" style=\"fill:var(--accent-text)\"/><text class=\"lb\" x=\"14.0\" y=\"118.8\" text-anchor=\"middle\" dominant-baseline=\"middle\">20 m</text><text class=\"lb\" x=\"132.8\" y=\"190.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">?</text></svg><div class=\"ex\"><div class=\"exh\">Worked example 1 · Horizontal launch</div><div class=\"exl\">12 m/s off a 20 m cliff: 20 = 5t², t = 2.0 s; x = 12 × 2.0 = <b>24 m</b>; v<sub>y</sub> = 20 m/s at landing, speed ≈ 23.3 m/s.</div></div><div class=\"ex\"><div class=\"exh\">Worked example 2 · Angled launch</div><div class=\"exl\">20 m/s at 30°: v<sub>x</sub> ≈ 17.3 m/s, v<sub>y0</sub> = 10 m/s.<br>Time of flight 2.0 s, range ≈ 34.6 m, maximum height 5.0 m. 60° gives the same range but goes higher.</div></div><div class=\"keybox\"><b>At the top</b> only v<sub>y</sub> is zero; v<sub>x</sub> is unchanged. Maximum range on level ground is at 45°.</div><div class=\"hub-btns\" style=\"margin-top:12px\"><button class=\"hub-btn primary\" data-go=\"s10\">Practise 1.5.A →</button><button class=\"hub-btn primary\" data-go=\"s11\">Practise 1.5.B →</button></div></section><section class=\"note\" id=\"nsum\"><h2>Unit checklist</h2><ul><li><b>1.1.A</b> Describe a scalar or vector quantity using magnitude and direction, as appropriate.</li><li><b>1.1.B</b> Describe a vector sum in one dimension.</li><li><b>1.2.A</b> Describe a change in an object's position.</li><li><b>1.2.B</b> Describe the average velocity and acceleration of an object.</li><li><b>1.3.A (i)</b> Describe the position, velocity and acceleration of an object using graphs of its motion.</li><li><b>1.3.A (ii)</b> Describe the position, velocity and acceleration of an object using the equations for constant acceleration.</li><li><b>1.3.A (iii)</b> Describe the motion of an object in free fall near Earth's surface (g ≈ 10 m/s² downward).</li><li><b>1.4.A</b> Describe the reference frame of a given observer.</li><li><b>1.4.B</b> Describe the motion of objects as measured by observers in different inertial reference frames.</li><li><b>1.5.A</b> Describe the perpendicular components of a vector.</li><li><b>1.5.B</b> Describe the motion of an object moving in two dimensions (projectiles).</li></ul><div class=\"hub-btns\" style=\"margin-top:10px\"><button class=\"hub-btn\" data-go=\"s12\">Test A</button><button class=\"hub-btn\" data-go=\"s13\">Test B</button><button class=\"hub-btn\" data-go=\"s14\">Test C</button><button class=\"hub-btn\" data-go=\"s15\">Test D</button><button class=\"hub-btn primary\" data-go=\"report\">📊 Report</button></div></section>";
var REPORT = [["s12", "A", "Knowing and understanding"], ["s13", "B", "Investigating patterns"], ["s14", "C", "Communicating"], ["s15", "D", "Applying physics in real-life contexts"]];
var SECTIONS = [{"id": "s1", "label": "1.1.A", "sub": "Scalars and vectors — LO 1.1.A: describe a scalar or vector quantity using magnitude and direction, as appropriate.", "slides": [{"kind": "mcq", "text": "Which of these is a vector quantity?", "opts": ["velocity", "speed", "time", "distance"], "correct": 0, "tag": "", "sol": "Velocity has magnitude and direction; the others have magnitude only."}, {"kind": "mcq", "text": "Which of these is a scalar quantity?", "opts": ["acceleration", "speed", "displacement", "position"], "correct": 1, "tag": "", "sol": "Speed is the magnitude of velocity; the others are vectors."}, {"kind": "mcq", "text": "Which pair are both vectors?", "opts": ["distance and speed", "time and displacement", "displacement and acceleration", "speed and acceleration"], "correct": 2, "tag": "", "sol": "Displacement and acceleration both have direction."}, {"kind": "mcq", "text": "With east as positive, a velocity of −4 m/s means", "opts": ["−4 m/s of speed", "4 m/s towards the west", "4 m/s towards the east", "slowing down at 4 m/s"], "correct": 1, "tag": "", "sol": "The sign gives the direction: negative = opposite to the positive (east) direction."}, {"kind": "mcq", "text": "What is the magnitude of a velocity v_x = −12 m/s?", "opts": ["144 m/s", "−12 m/s", "0", "12 m/s"], "correct": 3, "tag": "", "sol": "Magnitude is the size without the sign: 12 m/s."}, {"kind": "mcq", "text": "Two velocity arrows are drawn to the same scale. Arrow P is twice as long as arrow Q and points the opposite way. Which is true?", "opts": ["v_P = 2v_Q", "|v_P| = 2|v_Q| and they point in opposite directions", "P is slower than Q", "they have equal magnitudes"], "correct": 1, "tag": "", "sol": "Arrow length shows magnitude; arrow direction shows direction."}, {"kind": "blank", "p": "Classify each quantity as scalar or vector.", "tag": "", "marks": "", "flat": [{"t": "distance: __B1__", "a": {"B1": "scalar"}, "expr": "words"}, {"t": "displacement: __B1__", "a": {"B1": "vector"}, "expr": "words"}, {"t": "speed: __B1__", "a": {"B1": "scalar"}, "expr": "words"}, {"t": "acceleration: __B1__", "a": {"B1": "vector"}, "expr": "words"}], "sol": "Magnitude only.\nChange in position, with direction.\nMagnitude of velocity.\nRate of change of velocity, with direction."}, {"kind": "blank", "p": "Take right as positive. A cart has v_x = −6 m/s.", "tag": "", "marks": "", "flat": [{"t": "Its speed is __B1__ m/s.", "a": {"B1": "6"}}, {"t": "It moves to the __B1__.", "a": {"B1": "left"}, "expr": "words"}, {"t": "A cart moving right at 2.5 m/s has v_x = __B1__ m/s.", "a": {"B1": "2.5"}}], "sol": "Speed = |v_x| = 6 m/s.\nNegative = opposite to right.\n+2.5 m/s."}]}, {"id": "s2", "label": "1.1.B", "sub": "Vector addition in one dimension — LO 1.1.B: describe a vector sum in one dimension.", "slides": [{"kind": "mcq", "text": "A robot moves +5 m and then −8 m. What is its displacement?", "opts": ["−3 m", "+3 m", "+13 m", "−13 m"], "correct": 0, "tag": "", "sol": "5 + (−8) = −3 m."}, {"kind": "mcq", "text": "A walker goes 7 m east then 3 m west. Her displacement is", "opts": ["10 m west", "4 m west", "4 m east", "10 m east"], "correct": 2, "tag": "", "sol": "+7 − 3 = +4 m, i.e. east."}, {"kind": "mcq", "text": "A dog runs 20 m north, 35 m south, then 10 m north. Its displacement is", "opts": ["5 m north", "65 m", "5 m south", "25 m south"], "correct": 2, "tag": "", "sol": "+20 − 35 + 10 = −5 m, i.e. 5 m south."}, {"kind": "mcq", "text": "In one dimension, two displacements of 3 m and 4 m are added. Which results are possible?", "opts": ["7 m or 1 m only", "5 m only", "any value from 1 m to 7 m", "12 m"], "correct": 0, "tag": "", "sol": "In 1D they are either in the same direction (7 m) or opposite (1 m)."}, {"kind": "mcq", "text": "A car's velocity changes from +15 m/s to −5 m/s. What is Δv?", "opts": ["+20 m/s", "+10 m/s", "−10 m/s", "−20 m/s"], "correct": 3, "tag": "", "sol": "Δv = v_f − v_i = −5 − 15 = −20 m/s."}, {"kind": "mcq", "text": "A lift goes up 12 m, down 20 m, then up 8 m. Which is true?", "opts": ["Displacement 16 m up; distance 40 m", "Displacement 40 m; distance 0", "Displacement 0; distance 40 m", "Displacement 8 m up; distance 40 m"], "correct": 2, "tag": "", "sol": "+12 − 20 + 8 = 0; 12 + 20 + 8 = 40 m."}, {"kind": "blank", "p": "A robot moves +12 m, then −7 m, then +4 m.", "tag": "", "marks": "", "flat": [{"t": "Displacement = __B1__ m", "a": {"B1": "9"}}, {"t": "Distance = __B1__ m", "a": {"B1": "23"}}], "sol": "12 − 7 + 4 = 9 m.\n12 + 7 + 4 = 23 m."}, {"kind": "blank", "p": "A ball moving at +8 m/s bounces back at −6 m/s.", "tag": "", "marks": "", "flat": [{"t": "Δv = __B1__ m/s", "a": {"B1": "-14"}}, {"t": "Δv points in the __B1__ direction (positive / negative).", "a": {"B1": "negative"}, "expr": "words", "accept": ["backward", "backwards", "opposite", "minus"]}], "sol": "−6 − 8 = −14 m/s.\nThe change is negative (back the way it came)."}]}, {"id": "s3", "label": "1.2.A", "sub": "Change in position — LO 1.2.A: describe a change in an object's position.", "slides": [{"kind": "mcq", "text": "Displacement is defined as", "opts": ["final position − initial position", "initial position − final position", "total path length", "speed × time"], "correct": 0, "tag": "", "sol": "Δx = x_f − x_i."}, {"kind": "mcq", "text": "A bead moves from x = −3 m to x = +5 m. Its displacement is", "opts": ["+8 m", "+2 m", "+5 m", "−8 m"], "correct": 0, "tag": "", "sol": "5 − (−3) = +8 m."}, {"kind": "mcq", "text": "A toy car moves from x = 10 m to x = 4 m. Its displacement is", "opts": ["−6 m", "−14 m", "+6 m", "+14 m"], "correct": 0, "tag": "", "sol": "4 − 10 = −6 m."}, {"kind": "mcq", "text": "In the object model, a moving car is treated as", "opts": ["a set of wheels", "a point, ignoring its size and shape", "a wave", "a rigid box"], "correct": 1, "tag": "", "sol": "The object model ignores size and shape so only the position of one point matters."}, {"kind": "mcq", "text": "A runner goes 40 m out along a straight track and 15 m back. Which is correct?", "opts": ["distance 55 m, displacement 25 m", "distance 25 m, displacement 55 m", "both 55 m", "both 25 m"], "correct": 0, "tag": "", "sol": "Distance adds lengths; displacement is net change in position."}, {"kind": "mcq", "text": "Priya walks 30 m east and then 40 m west. What is her displacement?", "opts": ["10 m west", "10 m east", "70 m", "70 m west"], "correct": 0, "tag": "", "sol": "Take east as +: +30 − 40 = −10 m, i.e. 10 m west. (70 m is the distance.)"}, {"kind": "blank", "p": "A car is at x = 0 at t = 0, at x = +30 m at t = 2 s and at x = +10 m at t = 5 s. It moves steadily in one direction in each interval and turns round only at t = 2 s.", "tag": "", "marks": "", "flat": [{"t": "Displacement from 0 to 2 s = __B1__ m", "a": {"B1": "30"}}, {"t": "Displacement from 2 s to 5 s = __B1__ m", "a": {"B1": "-20"}}, {"t": "Displacement from 0 to 5 s = __B1__ m", "a": {"B1": "10"}}, {"t": "Distance travelled = __B1__ m", "a": {"B1": "50"}}], "sol": "30 − 0 = +30 m.\n10 − 30 = −20 m.\n10 − 0 = +10 m.\n30 + 20 = 50 m."}, {"kind": "blank", "p": "A bead starts at x = −4 m, moves to x = +6 m, then to x = +1 m.", "tag": "", "marks": "", "flat": [{"t": "First displacement = __B1__ m", "a": {"B1": "10"}}, {"t": "Second displacement = __B1__ m", "a": {"B1": "-5"}}, {"t": "Total displacement = __B1__ m", "a": {"B1": "5"}}, {"t": "Total distance = __B1__ m", "a": {"B1": "15"}}], "sol": "6 − (−4) = 10 m.\n1 − 6 = −5 m.\n1 − (−4) = 5 m.\n10 + 5 = 15 m."}]}, {"id": "s4", "label": "1.2.B", "sub": "Average velocity and acceleration — LO 1.2.B: describe the average velocity and acceleration of an object.", "slides": [{"kind": "mcq", "text": "A runner completes one lap of a 400 m track in 80 s and finishes where she started. What are her average speed and average velocity?", "opts": ["5 m/s and 5 m/s", "80 m/s and 0 m/s", "0 m/s and 5 m/s", "5 m/s and 0 m/s"], "correct": 3, "tag": "", "sol": "Average speed = 400 ÷ 80 = 5 m/s. Displacement is 0 (same start and finish), so average velocity = 0."}, {"kind": "mcq", "text": "A car travels 120 km in 1.5 h. What is its average speed?", "opts": ["120 km/h", "60 km/h", "80 km/h", "180 km/h"], "correct": 2, "tag": "", "sol": "120 ÷ 1.5 = 80 km/h."}, {"kind": "mcq", "text": "A toy car moves 4.0 m north in 1.0 s, then 5.0 m/s south for 3.0 s. What is its average velocity for the 4.0 s?", "opts": ["4.75 m/s south", "2.75 m/s north", "4.75 m/s", "2.75 m/s south"], "correct": 3, "tag": "", "sol": "Displacement = +4.0 − 15.0 = −11.0 m (south). Average velocity = 11.0 ÷ 4.0 = 2.75 m/s south. (4.75 m/s is the average speed: 19 m ÷ 4 s.)", "tools": ["calc"]}, {"kind": "mcq", "text": "A speed of 72 km/h is the same as", "opts": ["7.2 m/s", "20 m/s", "2 m/s", "259 m/s"], "correct": 1, "tag": "", "sol": "72 ÷ 3.6 = 20 m/s."}, {"kind": "mcq", "text": "A car speeds up from rest to 27 m/s in 9.0 s. Its average acceleration is", "opts": ["3.0 m/s²", "18 m/s²", "243 m/s²", "0.33 m/s²"], "correct": 0, "tag": "", "sol": "27 ÷ 9.0 = 3.0 m/s².", "tools": ["calc"]}, {"kind": "mcq", "text": "A car drives round a bend at a constant 15 m/s. Is it accelerating?", "opts": ["No, because its speed is constant", "Only if it speeds up", "Only if it slows down", "Yes, because the direction of its velocity changes"], "correct": 3, "tag": "", "sol": "Acceleration is any change in velocity, including a change of direction."}, {"kind": "mcq", "text": "An object's velocity changes from 10 m/s east to 10 m/s north in 5.0 s. Its average acceleration points", "opts": ["north", "it has no acceleration", "north-west", "north-east"], "correct": 2, "tag": "", "sol": "Δv = (10 north) + (10 west) points north-west; a ≈ 14.1 ÷ 5 ≈ 2.8 m/s²."}, {"kind": "blank", "p": "Meera walks 150 m east in 120 s, then 60 m west in 60 s.", "tag": "", "marks": "", "flat": [{"t": "Total distance = __B1__ m", "a": {"B1": "210"}}, {"t": "Displacement = __B1__ m east", "a": {"B1": "90"}}, {"t": "Average speed = __B1__ m/s (2 d.p.)", "a": {"B1": "1.17"}, "expr": "approx", "accept": ["1.17"]}, {"t": "Average velocity = __B1__ m/s east", "a": {"B1": "0.5"}}], "sol": "150 + 60 = 210 m.\n150 − 60 = 90 m east.\n210 ÷ 180 ≈ 1.17 m/s.\n90 ÷ 180 = 0.50 m/s east.", "tools": ["calc"]}, {"kind": "blank", "p": "Convert between km/h and m/s.", "tag": "", "marks": "", "flat": [{"t": "54 km/h = __B1__ m/s", "a": {"B1": "15"}}, {"t": "25 m/s = __B1__ km/h", "a": {"B1": "90"}}, {"t": "A car at 108 km/h covers __B1__ m in 1 s.", "a": {"B1": "30"}}], "sol": "54 ÷ 3.6 = 15.\n25 × 3.6 = 90.\n108 ÷ 3.6 = 30 m/s, so 30 m each second.", "tools": ["calc"]}, {"kind": "blank", "p": "A car moving at 18 m/s slows steadily to 6 m/s in 4.0 s.", "tag": "", "marks": "", "flat": [{"t": "Average acceleration = __B1__ m/s²", "a": {"B1": "-3"}}, {"t": "The acceleration points __B1__ to the velocity (along / opposite).", "a": {"B1": "opposite"}, "expr": "words"}], "sol": "(6 − 18) ÷ 4.0 = −3 m/s².\nIt slows down, so a is opposite to v.", "tools": ["calc"]}, {"kind": "blank", "p": "A cyclist covers 6.0 km in 20 minutes at constant speed.", "tag": "", "marks": "", "flat": [{"t": "Speed = __B1__ m/s", "a": {"B1": "5"}}, {"t": "Time to cover 15 km at the same speed = __B1__ minutes", "a": {"B1": "50"}}], "sol": "6000 m ÷ 1200 s = 5 m/s.\n15 000 ÷ 5 = 3000 s = 50 min.", "tools": ["calc"]}]}, {"id": "s5", "label": "1.3.A (i)", "sub": "Motion graphs — LO 1.3.A: describe the position, velocity and acceleration of an object using graphs of its motion.", "slides": [{"kind": "mcq", "text": "What does the slope of a position–time graph represent?", "opts": ["velocity", "acceleration", "displacement", "distance"], "correct": 0, "tag": "", "sol": "Slope = Δx ÷ Δt = velocity."}, {"kind": "mcq", "text": "What does the area under a velocity–time graph represent?", "opts": ["acceleration", "velocity", "time", "displacement"], "correct": 3, "tag": "", "sol": "Area = velocity × time = displacement (with sign)."}, {"kind": "mcq", "text": "On a position–time graph, a horizontal straight line means the object is", "opts": ["accelerating", "at rest", "moving backwards", "moving at constant velocity"], "correct": 1, "tag": "", "sol": "Position is not changing, so the velocity is zero."}, {"kind": "mcq", "text": "A velocity–time graph is a straight line starting at the origin and sloping upwards. The object is", "opts": ["slowing down", "moving at constant velocity", "accelerating uniformly from rest", "at rest"], "correct": 2, "tag": "", "sol": "Constant slope = constant acceleration; v = 0 at t = 0 means it started from rest."}, {"kind": "mcq", "text": "In the position–time graph shown, during which interval is the object at rest?", "opts": ["0 s to 2 s", "it is never at rest", "2 s to 5 s", "5 s to 7 s"], "correct": 2, "tag": "", "sol": "Between 2 s and 5 s the position stays at 8 m (horizontal line).", "fig": "<svg class=\"figsvg\" viewBox=\"0 0 320 230\" role=\"img\"><defs><marker id=\"ah\" viewBox=\"0 0 10 10\" refX=\"9\" refY=\"5\" markerWidth=\"7\" markerHeight=\"7\" orient=\"auto\"><path d=\"M0,1 L10,5 L0,9 z\" class=\"ahd\"/></marker><marker id=\"ahs\" viewBox=\"0 0 10 10\" refX=\"1\" refY=\"5\" markerWidth=\"7\" markerHeight=\"7\" orient=\"auto\"><path d=\"M10,1 L0,5 L10,9 z\" class=\"ahd\"/></marker></defs><line style=\"stroke:var(--rule)\" x1=\"46.0\" y1=\"196\" x2=\"46.0\" y2=\"18\"/><text class=\"po\" x=\"46.0\" y=\"209.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">0</text><line style=\"stroke:var(--rule)\" x1=\"82.3\" y1=\"196\" x2=\"82.3\" y2=\"18\"/><text class=\"po\" x=\"82.3\" y=\"209.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">1</text><line style=\"stroke:var(--rule)\" x1=\"118.6\" y1=\"196\" x2=\"118.6\" y2=\"18\"/><text class=\"po\" x=\"118.6\" y=\"209.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">2</text><line style=\"stroke:var(--rule)\" x1=\"154.9\" y1=\"196\" x2=\"154.9\" y2=\"18\"/><text class=\"po\" x=\"154.9\" y=\"209.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">3</text><line style=\"stroke:var(--rule)\" x1=\"191.1\" y1=\"196\" x2=\"191.1\" y2=\"18\"/><text class=\"po\" x=\"191.1\" y=\"209.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">4</text><line style=\"stroke:var(--rule)\" x1=\"227.4\" y1=\"196\" x2=\"227.4\" y2=\"18\"/><text class=\"po\" x=\"227.4\" y=\"209.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">5</text><line style=\"stroke:var(--rule)\" x1=\"263.7\" y1=\"196\" x2=\"263.7\" y2=\"18\"/><text class=\"po\" x=\"263.7\" y=\"209.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">6</text><line style=\"stroke:var(--rule)\" x1=\"300.0\" y1=\"196\" x2=\"300.0\" y2=\"18\"/><text class=\"po\" x=\"300.0\" y=\"209.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">7</text><line style=\"stroke:var(--rule)\" x1=\"46\" y1=\"196.0\" x2=\"300\" y2=\"196.0\"/><text class=\"po\" x=\"40.0\" y=\"196.0\" text-anchor=\"end\" dominant-baseline=\"middle\">0</text><line style=\"stroke:var(--rule)\" x1=\"46\" y1=\"160.4\" x2=\"300\" y2=\"160.4\"/><text class=\"po\" x=\"40.0\" y=\"160.4\" text-anchor=\"end\" dominant-baseline=\"middle\">2</text><line style=\"stroke:var(--rule)\" x1=\"46\" y1=\"124.8\" x2=\"300\" y2=\"124.8\"/><text class=\"po\" x=\"40.0\" y=\"124.8\" text-anchor=\"end\" dominant-baseline=\"middle\">4</text><line style=\"stroke:var(--rule)\" x1=\"46\" y1=\"89.2\" x2=\"300\" y2=\"89.2\"/><text class=\"po\" x=\"40.0\" y=\"89.2\" text-anchor=\"end\" dominant-baseline=\"middle\">6</text><line style=\"stroke:var(--rule)\" x1=\"46\" y1=\"53.6\" x2=\"300\" y2=\"53.6\"/><text class=\"po\" x=\"40.0\" y=\"53.6\" text-anchor=\"end\" dominant-baseline=\"middle\">8</text><line style=\"stroke:var(--rule)\" x1=\"46\" y1=\"18.0\" x2=\"300\" y2=\"18.0\"/><text class=\"po\" x=\"40.0\" y=\"18.0\" text-anchor=\"end\" dominant-baseline=\"middle\">10</text><line class=\"ln\" x1=\"46.0\" y1=\"196.0\" x2=\"308.0\" y2=\"196.0\" marker-end=\"url(#ah)\"/><line class=\"ln\" x1=\"46.0\" y1=\"196.0\" x2=\"46.0\" y2=\"10.0\" marker-end=\"url(#ah)\"/><text class=\"lb\" x=\"300.0\" y=\"188.0\" text-anchor=\"end\" dominant-baseline=\"middle\">t (s)</text><text class=\"lb\" x=\"52.0\" y=\"12.0\" text-anchor=\"start\" dominant-baseline=\"middle\">x (m)</text><polyline fill=\"none\" style=\"stroke:var(--danger);stroke-width:2.2\" points=\"46.0,196.0 118.6,53.6 227.4,53.6 300.0,196.0\"/><circle cx=\"46.0\" cy=\"196.0\" r=\"3\" style=\"fill:var(--danger)\"/><circle cx=\"118.6\" cy=\"53.6\" r=\"3\" style=\"fill:var(--danger)\"/><circle cx=\"227.4\" cy=\"53.6\" r=\"3\" style=\"fill:var(--danger)\"/><circle cx=\"300.0\" cy=\"196.0\" r=\"3\" style=\"fill:var(--danger)\"/></svg>"}, {"kind": "mcq", "text": "On a velocity–time graph, where does the object change direction?", "opts": ["where the graph is steepest", "where the graph crosses the time axis", "where the graph is horizontal", "at the highest point of the graph"], "correct": 1, "tag": "", "sol": "The velocity changes sign (from + to − or back) where v = 0 and the line crosses the axis."}, {"kind": "mcq", "text": "From rest, an object has a constant acceleration of 2 m/s² for 5 s. What is its speed at 5 s?", "opts": ["10 m/s", "25 m/s", "7 m/s", "2.5 m/s"], "correct": 0, "tag": "", "sol": "Area under the a–t graph = Δv = 2 × 5 = 10 m/s."}, {"kind": "mcq", "text": "The position–time graph shown curves upwards more and more steeply. The object is", "opts": ["moving at constant speed", "moving backwards", "speeding up", "slowing down"], "correct": 2, "tag": "", "sol": "The slope (velocity) keeps increasing, so it is speeding up.", "fig": "<svg class=\"figsvg\" viewBox=\"0 0 320 230\" role=\"img\"><defs><marker id=\"ah\" viewBox=\"0 0 10 10\" refX=\"9\" refY=\"5\" markerWidth=\"7\" markerHeight=\"7\" orient=\"auto\"><path d=\"M0,1 L10,5 L0,9 z\" class=\"ahd\"/></marker><marker id=\"ahs\" viewBox=\"0 0 10 10\" refX=\"1\" refY=\"5\" markerWidth=\"7\" markerHeight=\"7\" orient=\"auto\"><path d=\"M10,1 L0,5 L10,9 z\" class=\"ahd\"/></marker></defs><line style=\"stroke:var(--rule)\" x1=\"46.0\" y1=\"196\" x2=\"46.0\" y2=\"18\"/><text class=\"po\" x=\"46.0\" y=\"209.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">0</text><line style=\"stroke:var(--rule)\" x1=\"109.5\" y1=\"196\" x2=\"109.5\" y2=\"18\"/><text class=\"po\" x=\"109.5\" y=\"209.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">1</text><line style=\"stroke:var(--rule)\" x1=\"173.0\" y1=\"196\" x2=\"173.0\" y2=\"18\"/><text class=\"po\" x=\"173.0\" y=\"209.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">2</text><line style=\"stroke:var(--rule)\" x1=\"236.5\" y1=\"196\" x2=\"236.5\" y2=\"18\"/><text class=\"po\" x=\"236.5\" y=\"209.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">3</text><line style=\"stroke:var(--rule)\" x1=\"300.0\" y1=\"196\" x2=\"300.0\" y2=\"18\"/><text class=\"po\" x=\"300.0\" y=\"209.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">4</text><line style=\"stroke:var(--rule)\" x1=\"46\" y1=\"196.0\" x2=\"300\" y2=\"196.0\"/><text class=\"po\" x=\"40.0\" y=\"196.0\" text-anchor=\"end\" dominant-baseline=\"middle\">0</text><line style=\"stroke:var(--rule)\" x1=\"46\" y1=\"151.5\" x2=\"300\" y2=\"151.5\"/><text class=\"po\" x=\"40.0\" y=\"151.5\" text-anchor=\"end\" dominant-baseline=\"middle\">2</text><line style=\"stroke:var(--rule)\" x1=\"46\" y1=\"107.0\" x2=\"300\" y2=\"107.0\"/><text class=\"po\" x=\"40.0\" y=\"107.0\" text-anchor=\"end\" dominant-baseline=\"middle\">4</text><line style=\"stroke:var(--rule)\" x1=\"46\" y1=\"62.5\" x2=\"300\" y2=\"62.5\"/><text class=\"po\" x=\"40.0\" y=\"62.5\" text-anchor=\"end\" dominant-baseline=\"middle\">6</text><line style=\"stroke:var(--rule)\" x1=\"46\" y1=\"18.0\" x2=\"300\" y2=\"18.0\"/><text class=\"po\" x=\"40.0\" y=\"18.0\" text-anchor=\"end\" dominant-baseline=\"middle\">8</text><line class=\"ln\" x1=\"46.0\" y1=\"196.0\" x2=\"308.0\" y2=\"196.0\" marker-end=\"url(#ah)\"/><line class=\"ln\" x1=\"46.0\" y1=\"196.0\" x2=\"46.0\" y2=\"10.0\" marker-end=\"url(#ah)\"/><text class=\"lb\" x=\"300.0\" y=\"188.0\" text-anchor=\"end\" dominant-baseline=\"middle\">t (s)</text><text class=\"lb\" x=\"52.0\" y=\"12.0\" text-anchor=\"start\" dominant-baseline=\"middle\">x (m)</text><polyline fill=\"none\" style=\"stroke:var(--danger);stroke-width:2.2\" points=\"46.0,196.0 109.5,184.9 173.0,151.5 236.5,95.9 300.0,18.0\"/><circle cx=\"46.0\" cy=\"196.0\" r=\"3\" style=\"fill:var(--danger)\"/><circle cx=\"109.5\" cy=\"184.9\" r=\"3\" style=\"fill:var(--danger)\"/><circle cx=\"173.0\" cy=\"151.5\" r=\"3\" style=\"fill:var(--danger)\"/><circle cx=\"236.5\" cy=\"95.9\" r=\"3\" style=\"fill:var(--danger)\"/><circle cx=\"300.0\" cy=\"18.0\" r=\"3\" style=\"fill:var(--danger)\"/></svg>"}, {"kind": "blank", "p": "Use the velocity–time graph.", "tag": "", "marks": "", "flat": [{"t": "Acceleration from 0 s to 3 s = __B1__ m/s²", "a": {"B1": "3"}}, {"t": "Displacement in the first 3 s = __B1__ m", "a": {"B1": "13.5"}}, {"t": "Total displacement from 0 s to 12 s = __B1__ m", "a": {"B1": "81"}}, {"t": "Acceleration from 9 s to 12 s = __B1__ m/s²", "a": {"B1": "-3"}}], "sol": "9 ÷ 3 = 3 m/s².\n½ × 3 × 9 = 13.5 m.\n13.5 + 6 × 9 + ½ × 3 × 9 = 81 m.\n(0 − 9) ÷ 3 = −3 m/s².", "fig": "<svg class=\"figsvg\" viewBox=\"0 0 320 230\" role=\"img\"><defs><marker id=\"ah\" viewBox=\"0 0 10 10\" refX=\"9\" refY=\"5\" markerWidth=\"7\" markerHeight=\"7\" orient=\"auto\"><path d=\"M0,1 L10,5 L0,9 z\" class=\"ahd\"/></marker><marker id=\"ahs\" viewBox=\"0 0 10 10\" refX=\"1\" refY=\"5\" markerWidth=\"7\" markerHeight=\"7\" orient=\"auto\"><path d=\"M10,1 L0,5 L10,9 z\" class=\"ahd\"/></marker></defs><line style=\"stroke:var(--rule)\" x1=\"46.0\" y1=\"196\" x2=\"46.0\" y2=\"18\"/><text class=\"po\" x=\"46.0\" y=\"209.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">0</text><line style=\"stroke:var(--rule)\" x1=\"67.2\" y1=\"196\" x2=\"67.2\" y2=\"18\"/><text class=\"po\" x=\"67.2\" y=\"209.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">1</text><line style=\"stroke:var(--rule)\" x1=\"88.3\" y1=\"196\" x2=\"88.3\" y2=\"18\"/><text class=\"po\" x=\"88.3\" y=\"209.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">2</text><line style=\"stroke:var(--rule)\" x1=\"109.5\" y1=\"196\" x2=\"109.5\" y2=\"18\"/><text class=\"po\" x=\"109.5\" y=\"209.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">3</text><line style=\"stroke:var(--rule)\" x1=\"130.7\" y1=\"196\" x2=\"130.7\" y2=\"18\"/><text class=\"po\" x=\"130.7\" y=\"209.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">4</text><line style=\"stroke:var(--rule)\" x1=\"151.8\" y1=\"196\" x2=\"151.8\" y2=\"18\"/><text class=\"po\" x=\"151.8\" y=\"209.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">5</text><line style=\"stroke:var(--rule)\" x1=\"173.0\" y1=\"196\" x2=\"173.0\" y2=\"18\"/><text class=\"po\" x=\"173.0\" y=\"209.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">6</text><line style=\"stroke:var(--rule)\" x1=\"194.2\" y1=\"196\" x2=\"194.2\" y2=\"18\"/><text class=\"po\" x=\"194.2\" y=\"209.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">7</text><line style=\"stroke:var(--rule)\" x1=\"215.3\" y1=\"196\" x2=\"215.3\" y2=\"18\"/><text class=\"po\" x=\"215.3\" y=\"209.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">8</text><line style=\"stroke:var(--rule)\" x1=\"236.5\" y1=\"196\" x2=\"236.5\" y2=\"18\"/><text class=\"po\" x=\"236.5\" y=\"209.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">9</text><line style=\"stroke:var(--rule)\" x1=\"257.7\" y1=\"196\" x2=\"257.7\" y2=\"18\"/><text class=\"po\" x=\"257.7\" y=\"209.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">10</text><line style=\"stroke:var(--rule)\" x1=\"278.8\" y1=\"196\" x2=\"278.8\" y2=\"18\"/><text class=\"po\" x=\"278.8\" y=\"209.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">11</text><line style=\"stroke:var(--rule)\" x1=\"300.0\" y1=\"196\" x2=\"300.0\" y2=\"18\"/><text class=\"po\" x=\"300.0\" y=\"209.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">12</text><line style=\"stroke:var(--rule)\" x1=\"46\" y1=\"196.0\" x2=\"300\" y2=\"196.0\"/><text class=\"po\" x=\"40.0\" y=\"196.0\" text-anchor=\"end\" dominant-baseline=\"middle\">0</text><line style=\"stroke:var(--rule)\" x1=\"46\" y1=\"160.4\" x2=\"300\" y2=\"160.4\"/><text class=\"po\" x=\"40.0\" y=\"160.4\" text-anchor=\"end\" dominant-baseline=\"middle\">2</text><line style=\"stroke:var(--rule)\" x1=\"46\" y1=\"124.8\" x2=\"300\" y2=\"124.8\"/><text class=\"po\" x=\"40.0\" y=\"124.8\" text-anchor=\"end\" dominant-baseline=\"middle\">4</text><line style=\"stroke:var(--rule)\" x1=\"46\" y1=\"89.2\" x2=\"300\" y2=\"89.2\"/><text class=\"po\" x=\"40.0\" y=\"89.2\" text-anchor=\"end\" dominant-baseline=\"middle\">6</text><line style=\"stroke:var(--rule)\" x1=\"46\" y1=\"53.6\" x2=\"300\" y2=\"53.6\"/><text class=\"po\" x=\"40.0\" y=\"53.6\" text-anchor=\"end\" dominant-baseline=\"middle\">8</text><line style=\"stroke:var(--rule)\" x1=\"46\" y1=\"18.0\" x2=\"300\" y2=\"18.0\"/><text class=\"po\" x=\"40.0\" y=\"18.0\" text-anchor=\"end\" dominant-baseline=\"middle\">10</text><line class=\"ln\" x1=\"46.0\" y1=\"196.0\" x2=\"308.0\" y2=\"196.0\" marker-end=\"url(#ah)\"/><line class=\"ln\" x1=\"46.0\" y1=\"196.0\" x2=\"46.0\" y2=\"10.0\" marker-end=\"url(#ah)\"/><text class=\"lb\" x=\"300.0\" y=\"188.0\" text-anchor=\"end\" dominant-baseline=\"middle\">t (s)</text><text class=\"lb\" x=\"52.0\" y=\"12.0\" text-anchor=\"start\" dominant-baseline=\"middle\">v (m/s)</text><polyline fill=\"none\" style=\"stroke:var(--danger);stroke-width:2.2\" points=\"46.0,196.0 109.5,35.8 236.5,35.8 300.0,196.0\"/><circle cx=\"46.0\" cy=\"196.0\" r=\"3\" style=\"fill:var(--danger)\"/><circle cx=\"109.5\" cy=\"35.8\" r=\"3\" style=\"fill:var(--danger)\"/><circle cx=\"236.5\" cy=\"35.8\" r=\"3\" style=\"fill:var(--danger)\"/><circle cx=\"300.0\" cy=\"196.0\" r=\"3\" style=\"fill:var(--danger)\"/></svg>", "tools": ["calc", "desmos"], "desmos": ["y=3x\\{0\\le x\\le3\\}", "y=9\\{3\\le x\\le9\\}", "y=9-3(x-9)\\{9\\le x\\le12\\}"]}, {"kind": "blank", "p": "Use the position–time graph.", "tag": "", "marks": "", "flat": [{"t": "Velocity from 0 s to 2 s = __B1__ m/s", "a": {"B1": "4"}}, {"t": "Velocity from 5 s to 7 s = __B1__ m/s", "a": {"B1": "-4"}}, {"t": "Total distance travelled = __B1__ m", "a": {"B1": "16"}}, {"t": "Displacement at 7 s = __B1__ m", "a": {"B1": "0"}}], "sol": "8 ÷ 2 = 4 m/s.\n(0 − 8) ÷ 2 = −4 m/s (moving back).\n8 out + 8 back = 16 m.\nIt returns to x = 0: displacement 0.", "fig": "<svg class=\"figsvg\" viewBox=\"0 0 320 230\" role=\"img\"><defs><marker id=\"ah\" viewBox=\"0 0 10 10\" refX=\"9\" refY=\"5\" markerWidth=\"7\" markerHeight=\"7\" orient=\"auto\"><path d=\"M0,1 L10,5 L0,9 z\" class=\"ahd\"/></marker><marker id=\"ahs\" viewBox=\"0 0 10 10\" refX=\"1\" refY=\"5\" markerWidth=\"7\" markerHeight=\"7\" orient=\"auto\"><path d=\"M10,1 L0,5 L10,9 z\" class=\"ahd\"/></marker></defs><line style=\"stroke:var(--rule)\" x1=\"46.0\" y1=\"196\" x2=\"46.0\" y2=\"18\"/><text class=\"po\" x=\"46.0\" y=\"209.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">0</text><line style=\"stroke:var(--rule)\" x1=\"82.3\" y1=\"196\" x2=\"82.3\" y2=\"18\"/><text class=\"po\" x=\"82.3\" y=\"209.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">1</text><line style=\"stroke:var(--rule)\" x1=\"118.6\" y1=\"196\" x2=\"118.6\" y2=\"18\"/><text class=\"po\" x=\"118.6\" y=\"209.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">2</text><line style=\"stroke:var(--rule)\" x1=\"154.9\" y1=\"196\" x2=\"154.9\" y2=\"18\"/><text class=\"po\" x=\"154.9\" y=\"209.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">3</text><line style=\"stroke:var(--rule)\" x1=\"191.1\" y1=\"196\" x2=\"191.1\" y2=\"18\"/><text class=\"po\" x=\"191.1\" y=\"209.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">4</text><line style=\"stroke:var(--rule)\" x1=\"227.4\" y1=\"196\" x2=\"227.4\" y2=\"18\"/><text class=\"po\" x=\"227.4\" y=\"209.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">5</text><line style=\"stroke:var(--rule)\" x1=\"263.7\" y1=\"196\" x2=\"263.7\" y2=\"18\"/><text class=\"po\" x=\"263.7\" y=\"209.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">6</text><line style=\"stroke:var(--rule)\" x1=\"300.0\" y1=\"196\" x2=\"300.0\" y2=\"18\"/><text class=\"po\" x=\"300.0\" y=\"209.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">7</text><line style=\"stroke:var(--rule)\" x1=\"46\" y1=\"196.0\" x2=\"300\" y2=\"196.0\"/><text class=\"po\" x=\"40.0\" y=\"196.0\" text-anchor=\"end\" dominant-baseline=\"middle\">0</text><line style=\"stroke:var(--rule)\" x1=\"46\" y1=\"160.4\" x2=\"300\" y2=\"160.4\"/><text class=\"po\" x=\"40.0\" y=\"160.4\" text-anchor=\"end\" dominant-baseline=\"middle\">2</text><line style=\"stroke:var(--rule)\" x1=\"46\" y1=\"124.8\" x2=\"300\" y2=\"124.8\"/><text class=\"po\" x=\"40.0\" y=\"124.8\" text-anchor=\"end\" dominant-baseline=\"middle\">4</text><line style=\"stroke:var(--rule)\" x1=\"46\" y1=\"89.2\" x2=\"300\" y2=\"89.2\"/><text class=\"po\" x=\"40.0\" y=\"89.2\" text-anchor=\"end\" dominant-baseline=\"middle\">6</text><line style=\"stroke:var(--rule)\" x1=\"46\" y1=\"53.6\" x2=\"300\" y2=\"53.6\"/><text class=\"po\" x=\"40.0\" y=\"53.6\" text-anchor=\"end\" dominant-baseline=\"middle\">8</text><line style=\"stroke:var(--rule)\" x1=\"46\" y1=\"18.0\" x2=\"300\" y2=\"18.0\"/><text class=\"po\" x=\"40.0\" y=\"18.0\" text-anchor=\"end\" dominant-baseline=\"middle\">10</text><line class=\"ln\" x1=\"46.0\" y1=\"196.0\" x2=\"308.0\" y2=\"196.0\" marker-end=\"url(#ah)\"/><line class=\"ln\" x1=\"46.0\" y1=\"196.0\" x2=\"46.0\" y2=\"10.0\" marker-end=\"url(#ah)\"/><text class=\"lb\" x=\"300.0\" y=\"188.0\" text-anchor=\"end\" dominant-baseline=\"middle\">t (s)</text><text class=\"lb\" x=\"52.0\" y=\"12.0\" text-anchor=\"start\" dominant-baseline=\"middle\">x (m)</text><polyline fill=\"none\" style=\"stroke:var(--danger);stroke-width:2.2\" points=\"46.0,196.0 118.6,53.6 227.4,53.6 300.0,196.0\"/><circle cx=\"46.0\" cy=\"196.0\" r=\"3\" style=\"fill:var(--danger)\"/><circle cx=\"118.6\" cy=\"53.6\" r=\"3\" style=\"fill:var(--danger)\"/><circle cx=\"227.4\" cy=\"53.6\" r=\"3\" style=\"fill:var(--danger)\"/><circle cx=\"300.0\" cy=\"196.0\" r=\"3\" style=\"fill:var(--danger)\"/></svg>", "tools": ["calc"]}, {"kind": "blank", "p": "The velocity–time graph starts at +6 m/s and falls steadily to −6 m/s at 6 s.", "tag": "", "marks": "", "flat": [{"t": "Acceleration = __B1__ m/s²", "a": {"B1": "-2"}}, {"t": "The object turns round at t = __B1__ s", "a": {"B1": "3"}}, {"t": "Displacement from 0 to 3 s = __B1__ m", "a": {"B1": "9"}}, {"t": "Total distance from 0 to 6 s = __B1__ m", "a": {"B1": "18"}}], "sol": "(−6 − 6) ÷ 6 = −2 m/s².\nv = 0 at 3 s.\n½ × 3 × 6 = 9 m.\n9 m forward + 9 m back = 18 m (displacement 0).", "fig": "<svg class=\"figsvg\" viewBox=\"0 0 320 230\" role=\"img\"><defs><marker id=\"ah\" viewBox=\"0 0 10 10\" refX=\"9\" refY=\"5\" markerWidth=\"7\" markerHeight=\"7\" orient=\"auto\"><path d=\"M0,1 L10,5 L0,9 z\" class=\"ahd\"/></marker><marker id=\"ahs\" viewBox=\"0 0 10 10\" refX=\"1\" refY=\"5\" markerWidth=\"7\" markerHeight=\"7\" orient=\"auto\"><path d=\"M10,1 L0,5 L10,9 z\" class=\"ahd\"/></marker></defs><line style=\"stroke:var(--rule)\" x1=\"46.0\" y1=\"196\" x2=\"46.0\" y2=\"18\"/><text class=\"po\" x=\"46.0\" y=\"209.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">0</text><line style=\"stroke:var(--rule)\" x1=\"88.3\" y1=\"196\" x2=\"88.3\" y2=\"18\"/><text class=\"po\" x=\"88.3\" y=\"209.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">1</text><line style=\"stroke:var(--rule)\" x1=\"130.7\" y1=\"196\" x2=\"130.7\" y2=\"18\"/><text class=\"po\" x=\"130.7\" y=\"209.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">2</text><line style=\"stroke:var(--rule)\" x1=\"173.0\" y1=\"196\" x2=\"173.0\" y2=\"18\"/><text class=\"po\" x=\"173.0\" y=\"209.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">3</text><line style=\"stroke:var(--rule)\" x1=\"215.3\" y1=\"196\" x2=\"215.3\" y2=\"18\"/><text class=\"po\" x=\"215.3\" y=\"209.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">4</text><line style=\"stroke:var(--rule)\" x1=\"257.7\" y1=\"196\" x2=\"257.7\" y2=\"18\"/><text class=\"po\" x=\"257.7\" y=\"209.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">5</text><line style=\"stroke:var(--rule)\" x1=\"300.0\" y1=\"196\" x2=\"300.0\" y2=\"18\"/><text class=\"po\" x=\"300.0\" y=\"209.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">6</text><line style=\"stroke:var(--rule)\" x1=\"46\" y1=\"196.0\" x2=\"300\" y2=\"196.0\"/><text class=\"po\" x=\"40.0\" y=\"196.0\" text-anchor=\"end\" dominant-baseline=\"middle\">-6</text><line style=\"stroke:var(--rule)\" x1=\"46\" y1=\"166.3\" x2=\"300\" y2=\"166.3\"/><text class=\"po\" x=\"40.0\" y=\"166.3\" text-anchor=\"end\" dominant-baseline=\"middle\">-4</text><line style=\"stroke:var(--rule)\" x1=\"46\" y1=\"136.7\" x2=\"300\" y2=\"136.7\"/><text class=\"po\" x=\"40.0\" y=\"136.7\" text-anchor=\"end\" dominant-baseline=\"middle\">-2</text><line style=\"stroke:var(--rule)\" x1=\"46\" y1=\"107.0\" x2=\"300\" y2=\"107.0\"/><text class=\"po\" x=\"40.0\" y=\"107.0\" text-anchor=\"end\" dominant-baseline=\"middle\">0</text><line style=\"stroke:var(--rule)\" x1=\"46\" y1=\"77.3\" x2=\"300\" y2=\"77.3\"/><text class=\"po\" x=\"40.0\" y=\"77.3\" text-anchor=\"end\" dominant-baseline=\"middle\">2</text><line style=\"stroke:var(--rule)\" x1=\"46\" y1=\"47.7\" x2=\"300\" y2=\"47.7\"/><text class=\"po\" x=\"40.0\" y=\"47.7\" text-anchor=\"end\" dominant-baseline=\"middle\">4</text><line style=\"stroke:var(--rule)\" x1=\"46\" y1=\"18.0\" x2=\"300\" y2=\"18.0\"/><text class=\"po\" x=\"40.0\" y=\"18.0\" text-anchor=\"end\" dominant-baseline=\"middle\">6</text><line class=\"ln\" x1=\"46.0\" y1=\"196.0\" x2=\"308.0\" y2=\"196.0\" marker-end=\"url(#ah)\"/><line class=\"ln\" x1=\"46.0\" y1=\"196.0\" x2=\"46.0\" y2=\"10.0\" marker-end=\"url(#ah)\"/><text class=\"lb\" x=\"300.0\" y=\"188.0\" text-anchor=\"end\" dominant-baseline=\"middle\">t (s)</text><text class=\"lb\" x=\"52.0\" y=\"12.0\" text-anchor=\"start\" dominant-baseline=\"middle\">v (m/s)</text><polyline fill=\"none\" style=\"stroke:var(--danger);stroke-width:2.2\" points=\"46.0,18.0 300.0,196.0\"/><circle cx=\"46.0\" cy=\"18.0\" r=\"3\" style=\"fill:var(--danger)\"/><circle cx=\"300.0\" cy=\"196.0\" r=\"3\" style=\"fill:var(--danger)\"/></svg>", "tools": ["desmos"], "desmos": ["y=6-2x\\{0\\le x\\le6\\}"]}, {"kind": "blank", "p": "An object starts from rest. Its acceleration–time graph is shown.", "tag": "", "marks": "", "flat": [{"t": "Velocity at 4 s = __B1__ m/s", "a": {"B1": "12"}}, {"t": "Velocity at 6 s = __B1__ m/s", "a": {"B1": "12"}}, {"t": "Velocity at 8 s = __B1__ m/s", "a": {"B1": "8"}}], "sol": "Area 3 × 4 = 12 m/s.\na = 0 from 4 to 6 s: no change.\n12 + (−2 × 2) = 8 m/s.", "fig": "<svg class=\"figsvg\" viewBox=\"0 0 320 230\" role=\"img\"><defs><marker id=\"ah\" viewBox=\"0 0 10 10\" refX=\"9\" refY=\"5\" markerWidth=\"7\" markerHeight=\"7\" orient=\"auto\"><path d=\"M0,1 L10,5 L0,9 z\" class=\"ahd\"/></marker><marker id=\"ahs\" viewBox=\"0 0 10 10\" refX=\"1\" refY=\"5\" markerWidth=\"7\" markerHeight=\"7\" orient=\"auto\"><path d=\"M10,1 L0,5 L10,9 z\" class=\"ahd\"/></marker></defs><line style=\"stroke:var(--rule)\" x1=\"46.0\" y1=\"196\" x2=\"46.0\" y2=\"18\"/><text class=\"po\" x=\"46.0\" y=\"209.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">0</text><line style=\"stroke:var(--rule)\" x1=\"77.8\" y1=\"196\" x2=\"77.8\" y2=\"18\"/><text class=\"po\" x=\"77.8\" y=\"209.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">1</text><line style=\"stroke:var(--rule)\" x1=\"109.5\" y1=\"196\" x2=\"109.5\" y2=\"18\"/><text class=\"po\" x=\"109.5\" y=\"209.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">2</text><line style=\"stroke:var(--rule)\" x1=\"141.2\" y1=\"196\" x2=\"141.2\" y2=\"18\"/><text class=\"po\" x=\"141.2\" y=\"209.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">3</text><line style=\"stroke:var(--rule)\" x1=\"173.0\" y1=\"196\" x2=\"173.0\" y2=\"18\"/><text class=\"po\" x=\"173.0\" y=\"209.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">4</text><line style=\"stroke:var(--rule)\" x1=\"204.8\" y1=\"196\" x2=\"204.8\" y2=\"18\"/><text class=\"po\" x=\"204.8\" y=\"209.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">5</text><line style=\"stroke:var(--rule)\" x1=\"236.5\" y1=\"196\" x2=\"236.5\" y2=\"18\"/><text class=\"po\" x=\"236.5\" y=\"209.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">6</text><line style=\"stroke:var(--rule)\" x1=\"268.2\" y1=\"196\" x2=\"268.2\" y2=\"18\"/><text class=\"po\" x=\"268.2\" y=\"209.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">7</text><line style=\"stroke:var(--rule)\" x1=\"300.0\" y1=\"196\" x2=\"300.0\" y2=\"18\"/><text class=\"po\" x=\"300.0\" y=\"209.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">8</text><line style=\"stroke:var(--rule)\" x1=\"46\" y1=\"196.0\" x2=\"300\" y2=\"196.0\"/><text class=\"po\" x=\"40.0\" y=\"196.0\" text-anchor=\"end\" dominant-baseline=\"middle\">-3</text><line style=\"stroke:var(--rule)\" x1=\"46\" y1=\"170.6\" x2=\"300\" y2=\"170.6\"/><text class=\"po\" x=\"40.0\" y=\"170.6\" text-anchor=\"end\" dominant-baseline=\"middle\">-2</text><line style=\"stroke:var(--rule)\" x1=\"46\" y1=\"145.1\" x2=\"300\" y2=\"145.1\"/><text class=\"po\" x=\"40.0\" y=\"145.1\" text-anchor=\"end\" dominant-baseline=\"middle\">-1</text><line style=\"stroke:var(--rule)\" x1=\"46\" y1=\"119.7\" x2=\"300\" y2=\"119.7\"/><text class=\"po\" x=\"40.0\" y=\"119.7\" text-anchor=\"end\" dominant-baseline=\"middle\">0</text><line style=\"stroke:var(--rule)\" x1=\"46\" y1=\"94.3\" x2=\"300\" y2=\"94.3\"/><text class=\"po\" x=\"40.0\" y=\"94.3\" text-anchor=\"end\" dominant-baseline=\"middle\">1</text><line style=\"stroke:var(--rule)\" x1=\"46\" y1=\"68.9\" x2=\"300\" y2=\"68.9\"/><text class=\"po\" x=\"40.0\" y=\"68.9\" text-anchor=\"end\" dominant-baseline=\"middle\">2</text><line style=\"stroke:var(--rule)\" x1=\"46\" y1=\"43.4\" x2=\"300\" y2=\"43.4\"/><text class=\"po\" x=\"40.0\" y=\"43.4\" text-anchor=\"end\" dominant-baseline=\"middle\">3</text><line style=\"stroke:var(--rule)\" x1=\"46\" y1=\"18.0\" x2=\"300\" y2=\"18.0\"/><text class=\"po\" x=\"40.0\" y=\"18.0\" text-anchor=\"end\" dominant-baseline=\"middle\">4</text><line class=\"ln\" x1=\"46.0\" y1=\"196.0\" x2=\"308.0\" y2=\"196.0\" marker-end=\"url(#ah)\"/><line class=\"ln\" x1=\"46.0\" y1=\"196.0\" x2=\"46.0\" y2=\"10.0\" marker-end=\"url(#ah)\"/><text class=\"lb\" x=\"300.0\" y=\"188.0\" text-anchor=\"end\" dominant-baseline=\"middle\">t (s)</text><text class=\"lb\" x=\"52.0\" y=\"12.0\" text-anchor=\"start\" dominant-baseline=\"middle\">a (m/s²)</text><polyline fill=\"none\" style=\"stroke:var(--danger);stroke-width:2.2\" points=\"46.0,43.4 173.0,43.4 173.0,119.7 236.5,119.7 236.5,170.6 300.0,170.6\"/><circle cx=\"46.0\" cy=\"43.4\" r=\"3\" style=\"fill:var(--danger)\"/><circle cx=\"173.0\" cy=\"43.4\" r=\"3\" style=\"fill:var(--danger)\"/><circle cx=\"173.0\" cy=\"119.7\" r=\"3\" style=\"fill:var(--danger)\"/><circle cx=\"236.5\" cy=\"119.7\" r=\"3\" style=\"fill:var(--danger)\"/><circle cx=\"236.5\" cy=\"170.6\" r=\"3\" style=\"fill:var(--danger)\"/><circle cx=\"300.0\" cy=\"170.6\" r=\"3\" style=\"fill:var(--danger)\"/></svg>", "tools": ["calc"]}]}, {"id": "s6", "label": "1.3.A (ii)", "sub": "Kinematic equations — LO 1.3.A: describe the position, velocity and acceleration of an object using the equations for constant acceleration.", "slides": [{"kind": "mcq", "text": "A car accelerates uniformly from rest to 20 m/s in 8.0 s. What is its acceleration?", "opts": ["160 m/s²", "12 m/s²", "0.4 m/s²", "2.5 m/s²"], "correct": 3, "tag": "", "sol": "a = Δv ÷ t = 20 ÷ 8 = 2.5 m/s².", "tools": ["calc"]}, {"kind": "mcq", "text": "How far does that car travel in the 8.0 s?", "opts": ["20 m", "80 m", "40 m", "160 m"], "correct": 1, "tag": "", "sol": "Δx = ½(v₀ + v)t = ½(0 + 20)(8) = 80 m.", "tools": ["calc"]}, {"kind": "mcq", "text": "A car moving at 24 m/s brakes with a deceleration of 4.0 m/s². What is its stopping distance?", "opts": ["6 m", "72 m", "96 m", "144 m"], "correct": 1, "tag": "", "sol": "v² = v₀² + 2aΔx: 0 = 576 − 8Δx, Δx = 72 m.", "tools": ["calc"]}, {"kind": "mcq", "text": "If the car had been going twice as fast (same braking), its stopping distance would be", "opts": ["half as long", "4 times as long", "the same", "2 times as long"], "correct": 1, "tag": "", "sol": "Δx = v₀² ÷ 2a, so doubling v₀ multiplies Δx by 4."}, {"kind": "mcq", "text": "Which equation should you use when the time is not given and not asked for?", "opts": ["v = v₀ + at", "Δx = v₀t + ½at²", "Δx = ½(v₀ + v)t", "v² = v₀² + 2aΔx"], "correct": 3, "tag": "", "sol": "It is the only one of the four without t."}, {"kind": "mcq", "text": "An object starts from rest and moves a distance d in the first second with constant acceleration. How far does it move during the next second?", "opts": ["2d", "3d", "4d", "d"], "correct": 1, "tag": "", "sol": "Distance ∝ t²: after 2 s it has gone 4d, so the second second covers 4d − d = 3d."}, {"kind": "mcq", "text": "A cyclist moving at 4.0 m/s accelerates at 1.5 m/s² for 6.0 s. What is her final speed?", "opts": ["10 m/s", "9 m/s", "13 m/s", "31 m/s"], "correct": 2, "tag": "", "sol": "v = 4.0 + 1.5 × 6.0 = 13 m/s.", "tools": ["calc"]}, {"kind": "mcq", "text": "A train slows from 24 m/s to 6 m/s over 270 m. What is its acceleration?", "opts": ["−1.0 m/s²", "+1.0 m/s²", "−0.067 m/s²", "−2.0 m/s²"], "correct": 0, "tag": "", "sol": "a = (6² − 24²) ÷ (2 × 270) = (36 − 576) ÷ 540 = −1.0 m/s².", "tools": ["calc"]}, {"kind": "blank", "p": "A sprinter reaches 11 m/s in 2.2 s from rest, then runs the rest of a 100 m race at 11 m/s.", "tag": "", "marks": "", "flat": [{"t": "Acceleration = __B1__ m/s²", "a": {"B1": "5"}}, {"t": "Distance covered in the first 2.2 s = __B1__ m", "a": {"B1": "12.1"}, "expr": "approx"}, {"t": "Time for the remaining distance = __B1__ s", "a": {"B1": "7.99"}, "expr": "approx"}, {"t": "Total race time = __B1__ s", "a": {"B1": "10.2"}, "expr": "approx"}], "sol": "11 ÷ 2.2 = 5 m/s².\n½ × 5 × 2.2² = 12.1 m.\n(100 − 12.1) ÷ 11 ≈ 7.99 s.\n2.2 + 7.99 ≈ 10.2 s.", "tools": ["calc"]}, {"kind": "blank", "p": "A car moving at 25 m/s brakes with acceleration −6.25 m/s².", "tag": "", "marks": "", "flat": [{"t": "Time to stop = __B1__ s", "a": {"B1": "4"}}, {"t": "Stopping distance = __B1__ m", "a": {"B1": "50"}}], "sol": "0 = 25 − 6.25t, t = 4 s.\n½(25 + 0)(4) = 50 m.", "tools": ["calc"]}, {"kind": "blank", "p": "A cart rolling at 0.6 m/s comes to rest in 1.2 m with constant deceleration.", "tag": "", "marks": "", "flat": [{"t": "Acceleration = __B1__ m/s²", "a": {"B1": "-0.15"}}, {"t": "Starting at 1.2 m/s on the same track, it stops in __B1__ m.", "a": {"B1": "4.8"}}], "sol": "a = (0 − 0.36) ÷ 2.4 = −0.15 m/s².\nΔx = 1.44 ÷ 0.30 = 4.8 m (twice the speed, four times the distance).", "tools": ["calc"]}, {"kind": "blank", "p": "A bus starts from rest, accelerates at 1.5 m/s² for 8 s, then moves at constant speed for 20 s.", "tag": "", "marks": "", "flat": [{"t": "Speed after 8 s = __B1__ m/s", "a": {"B1": "12"}}, {"t": "Distance in the first 8 s = __B1__ m", "a": {"B1": "48"}}, {"t": "Total distance = __B1__ m", "a": {"B1": "288"}}], "sol": "1.5 × 8 = 12 m/s.\n½ × 1.5 × 8² = 48 m.\n48 + 12 × 20 = 288 m.", "tools": ["calc"]}, {"kind": "blank", "p": "A strobe photo of a toy car starting from rest shows its position every second: 0, 2, 8, 18 cm.", "tag": "", "marks": "", "flat": [{"t": "Distances covered in the 1st, 2nd and 3rd seconds (in cm): __B1__", "a": {"B1": "2, 6, 10"}, "expr": "dlist"}, {"t": "Acceleration = __B1__ cm/s²", "a": {"B1": "4"}}, {"t": "Position at t = 4 s = __B1__ cm", "a": {"B1": "32"}}], "sol": "2 − 0, 8 − 2, 18 − 8.\nEach second's distance grows by 4 cm, so a = 4 cm/s² (x = 2t²).\n2 × 4² = 32 cm."}]}, {"id": "s7", "label": "1.3.A (iii)", "sub": "Free fall — LO 1.3.A: describe the motion of an object in free fall near Earth's surface (g ≈ 10 m/s² downward).", "slides": [{"kind": "mcq", "text": "A ball is thrown straight up. At its highest point, its acceleration is", "opts": ["zero", "10 m/s² downward", "changing direction", "10 m/s² upward"], "correct": 1, "tag": "", "sol": "Gravity acts all the time: a = 10 m/s² down even though v = 0."}, {"kind": "mcq", "text": "A stone is dropped from rest. What is its speed after 3.0 s?", "opts": ["3.3 m/s", "30 m/s", "10 m/s", "45 m/s"], "correct": 1, "tag": "", "sol": "v = gt = 10 × 3.0 = 30 m/s."}, {"kind": "mcq", "text": "A ball dropped from a roof hits the ground at 30 m/s. How tall is the roof?", "opts": ["300 m", "45 m", "90 m", "15 m"], "correct": 1, "tag": "", "sol": "v² = 2gh: h = 900 ÷ 20 = 45 m."}, {"kind": "mcq", "text": "Ball X is thrown up with twice the speed of ball Y. X's maximum height is", "opts": ["4 times Y's", "the same", "2 times Y's", "√2 times Y's"], "correct": 0, "tag": "", "sol": "h = v₀² ÷ 2g."}, {"kind": "mcq", "text": "Object P falls from rest for 3 s; object Q for 6 s. Compared with P, Q falls", "opts": ["2 times as far", "4 times as far", "8 times as far", "3 times as far"], "correct": 1, "tag": "", "sol": "Distance ∝ t²."}, {"kind": "mcq", "text": "Two identical balls are dropped from a tall tower 1 s apart. While both fall, the distance between them", "opts": ["decreases", "stays the same", "first increases then decreases", "increases"], "correct": 3, "tag": "", "sol": "The first ball is always 10 m/s faster."}, {"kind": "mcq", "text": "Ignoring air resistance, a 5 kg ball and a 1 kg ball are dropped together. Which lands first?", "opts": ["They land together", "The 5 kg ball", "The 1 kg ball", "It depends on their size"], "correct": 0, "tag": "", "sol": "Free-fall acceleration does not depend on mass."}, {"kind": "mcq", "text": "A ball is thrown up at 20 m/s. After 3.0 s, what are the directions of its displacement, velocity and acceleration?", "opts": ["up, up, down", "up, down, up", "up, down, down", "down, down, down"], "correct": 2, "tag": "", "sol": "v = 20 − 30 = −10 m/s (down); Δy = 60 − 45 = +15 m (above start); a = 10 m/s² down."}, {"kind": "blank", "p": "A ball is thrown straight up at 20 m/s. Take up as positive.", "tag": "", "marks": "", "flat": [{"t": "Time to reach the top = __B1__ s", "a": {"B1": "2"}}, {"t": "Maximum height = __B1__ m", "a": {"B1": "20"}}, {"t": "Time to return to the hand = __B1__ s", "a": {"B1": "4"}}, {"t": "Speed when it returns = __B1__ m/s", "a": {"B1": "20"}}], "sol": "0 = 20 − 10t, t = 2 s.\nh = 20² ÷ 20 = 20 m.\nSymmetric: 4 s.\n20 m/s (downward).", "tools": ["calc", "desmos"], "desmos": ["y=20x-5x^2"]}, {"kind": "blank", "p": "A stone dropped from a bridge takes 3.0 s to reach the water.", "tag": "", "marks": "", "flat": [{"t": "Speed at the water = __B1__ m/s", "a": {"B1": "30"}}, {"t": "Height of the bridge = __B1__ m", "a": {"B1": "45"}}], "sol": "10 × 3.0 = 30 m/s.\n½ × 10 × 3.0² = 45 m.", "tools": ["calc"]}, {"kind": "blank", "p": "A ball is thrown straight down at 5.0 m/s from a height of 40 m.", "tag": "", "marks": "", "flat": [{"t": "Speed on reaching the ground = __B1__ m/s", "a": {"B1": "28.7"}, "expr": "approx"}, {"t": "Time taken = __B1__ s", "a": {"B1": "2.37"}, "expr": "approx"}], "sol": "v² = 25 + 2 × 10 × 40 = 825, v ≈ 28.7 m/s.\nt = (28.7 − 5.0) ÷ 10 ≈ 2.37 s.", "tools": ["calc"]}, {"kind": "blank", "p": "An object falls from rest. Find the distance fallen during each second.", "tag": "", "marks": "", "flat": [{"t": "1st second: __B1__ m", "a": {"B1": "5"}}, {"t": "2nd second: __B1__ m", "a": {"B1": "15"}}, {"t": "3rd second: __B1__ m", "a": {"B1": "25"}}, {"t": "Ratio 1 : 3 : __B1__", "a": {"B1": "5"}}], "sol": "½ × 10 × 1² = 5 m.\n20 − 5 = 15 m.\n45 − 20 = 25 m.\n5 : 15 : 25 = 1 : 3 : 5."}]}, {"id": "s8", "label": "1.4.A", "sub": "Reference frames — LO 1.4.A: describe the reference frame of a given observer.", "slides": [{"kind": "mcq", "text": "A passenger sits still in a moving train. Which statement is correct?", "opts": ["She is at rest in every frame", "She is at rest relative to the train but moving relative to the platform", "She is moving relative to the train", "She has no velocity"], "correct": 1, "tag": "", "sol": "Motion is always relative to a chosen frame."}, {"kind": "mcq", "text": "A girl on a platform sees a train pass at 20 m/s east. In the train's frame, the platform moves at", "opts": ["20 m/s west", "40 m/s west", "0 m/s", "20 m/s east"], "correct": 0, "tag": "", "sol": "Relative velocities are equal and opposite."}, {"kind": "mcq", "text": "A passenger on a smoothly moving train drops a ball. Its path is", "opts": ["a curve for both", "straight down for the passenger; a curve (parabola) for someone on the platform", "backwards for the passenger", "straight down for both"], "correct": 1, "tag": "", "sol": "The ball shares the train's horizontal velocity; only the platform observer sees that velocity."}, {"kind": "mcq", "text": "Moving the origin of a coordinate system 5 m to the left changes", "opts": ["the displacements but not the positions", "both", "neither", "the positions but not the displacements"], "correct": 3, "tag": "", "sol": "All positions shift by the same amount, so differences (displacements) are unchanged."}, {"kind": "mcq", "text": "Observer A takes east as positive; observer B takes west as positive. A car drives east at 12 m/s. B records its velocity as", "opts": ["−12 m/s", "+12 m/s", "24 m/s", "0"], "correct": 0, "tag": "", "sol": "Same motion, opposite sign convention."}, {"kind": "mcq", "text": "Which quantity is the same for every observer moving at constant velocity relative to one another?", "opts": ["the acceleration of an object", "the kinetic energy of an object", "the position of an object", "the velocity of an object"], "correct": 0, "tag": "", "sol": "Acceleration is the same in all inertial frames."}, {"kind": "blank", "p": "A book lies on a straight shelf 3 m to the right of a door. A window is 5 m to the left of the door. Take right as positive.", "tag": "", "marks": "", "flat": [{"t": "Book's position measured from the door = __B1__ m", "a": {"B1": "3"}}, {"t": "Book's position measured from the window = __B1__ m", "a": {"B1": "8"}}, {"t": "The book is moved to 1 m right of the door. Its displacement (either origin) = __B1__ m", "a": {"B1": "-2"}}], "sol": "+3 m.\n5 + 3 = 8 m.\n1 − 3 = −2 m in both frames."}, {"kind": "blank", "p": "A ball falls at 12 m/s with acceleration 10 m/s² downward. Observer A takes up as positive; observer B takes down as positive.", "tag": "", "marks": "", "flat": [{"t": "A records v = __B1__ m/s", "a": {"B1": "-12"}}, {"t": "B records v = __B1__ m/s", "a": {"B1": "12"}}, {"t": "A records a = __B1__ m/s²", "a": {"B1": "-10"}}, {"t": "Do A and B disagree about the actual motion? __B1__", "a": {"B1": "no"}, "expr": "words", "accept": ["n"]}], "sol": "Down is negative for A: −12 m/s.\nDown is positive for B: +12 m/s.\n−10 m/s² for A (+10 for B).\nNo: only the sign convention differs; the motion is the same."}]}, {"id": "s9", "label": "1.4.B", "sub": "Relative motion — LO 1.4.B: describe the motion of objects as measured by observers in different inertial reference frames.", "slides": [{"kind": "mcq", "text": "Two cars drive towards each other at 60 km/h and 40 km/h. Their speed relative to each other is", "opts": ["2400 km/h", "20 km/h", "50 km/h", "100 km/h"], "correct": 3, "tag": "", "sol": "Moving towards each other, the speeds add."}, {"kind": "mcq", "text": "A passenger walks towards the front of a train at 1.5 m/s. The train moves at 20 m/s. Her speed relative to the ground is", "opts": ["20 m/s", "1.5 m/s", "21.5 m/s", "18.5 m/s"], "correct": 2, "tag": "", "sol": "Same direction: 20 + 1.5 = 21.5 m/s."}, {"kind": "mcq", "text": "Two trains 260 km apart travel towards each other at 60 km/h and 70 km/h. When do they meet?", "opts": ["after 3.7 h", "after 2 h", "after 4.3 h", "after 26 h"], "correct": 1, "tag": "", "sol": "The gap closes at 60 + 70 = 130 km/h: 260 ÷ 130 = 2 h.", "tools": ["calc"]}, {"kind": "mcq", "text": "A car at 30 m/s is 150 m behind a truck at 20 m/s in the same lane, moving the same way. How long until the car catches up?", "opts": ["15 s", "5 s", "3 s", "7.5 s"], "correct": 0, "tag": "", "sol": "Relative velocity 10 m/s; 150 ÷ 10 = 15 s."}, {"kind": "mcq", "text": "Rain falls vertically at 6 m/s. To a driver moving at 8 m/s, the rain's speed appears to be", "opts": ["10 m/s", "6 m/s", "14 m/s", "2 m/s"], "correct": 0, "tag": "", "sol": "Add the perpendicular velocities: √(6² + 8²) = 10 m/s."}, {"kind": "mcq", "text": "A ball's acceleration is 10 m/s² down for an observer on the ground. For an observer in a lift moving up at a constant 3 m/s, it is", "opts": ["0", "7 m/s² down", "10 m/s² down", "13 m/s² down"], "correct": 2, "tag": "", "sol": "Accelerations are the same in all inertial frames."}, {"kind": "mcq", "text": "A boat moves at 5 m/s relative to the water, straight downstream in a river flowing at 2 m/s. Its speed relative to the bank is", "opts": ["5.4 m/s", "3 m/s", "5 m/s", "7 m/s"], "correct": 3, "tag": "", "sol": "Same direction: 5 + 2 = 7 m/s."}, {"kind": "blank", "p": "A swimmer swims straight across a 90 m wide river at 1.2 m/s. The current flows at 0.5 m/s.", "tag": "", "marks": "", "flat": [{"t": "Time to cross = __B1__ s", "a": {"B1": "75"}}, {"t": "Distance carried downstream = __B1__ m", "a": {"B1": "37.5"}}, {"t": "Speed relative to the bank = __B1__ m/s", "a": {"B1": "1.3"}}], "sol": "90 ÷ 1.2 = 75 s.\n0.5 × 75 = 37.5 m.\n√(1.2² + 0.5²) = √1.69 = 1.3 m/s.", "tools": ["calc"]}, {"kind": "blank", "p": "A girl uses an escalator that moves up at 0.8 m/s and is 24 m long.", "tag": "", "marks": "", "flat": [{"t": "Walking up it at 1.2 m/s, her speed relative to the ground = __B1__ m/s", "a": {"B1": "2"}}, {"t": "Time to reach the top = __B1__ s", "a": {"B1": "12"}}, {"t": "Walking down it at 1.2 m/s, her ground speed = __B1__ m/s", "a": {"B1": "0.4"}}], "sol": "0.8 + 1.2 = 2.0 m/s.\n24 ÷ 2.0 = 12 s.\n1.2 − 0.8 = 0.4 m/s downward.", "tools": ["calc"]}]}, {"id": "s10", "label": "1.5.A", "sub": "Vector components — LO 1.5.A: describe the perpendicular components of a vector.", "slides": [{"kind": "mcq", "text": "What is the size of the resultant of 3 m east and 4 m north?", "opts": ["5 m", "1 m", "12 m", "7 m"], "correct": 0, "tag": "", "sol": "√(3² + 4²) = 5 m."}, {"kind": "mcq", "text": "In what direction is that resultant?", "opts": ["53.1° north of east", "53.1° east of north", "45° north of east", "36.9° north of east"], "correct": 0, "tag": "", "sol": "tan θ = 4 ÷ 3, θ ≈ 53.1° measured from east towards north.", "tools": ["calc"]}, {"kind": "mcq", "text": "A velocity of 20 m/s at 30° above the horizontal has components", "opts": ["14.1 m/s each", "20 m/s horizontal, 0 vertical", "10 m/s horizontal, 17.3 m/s vertical", "17.3 m/s horizontal, 10 m/s vertical"], "correct": 3, "tag": "", "sol": "v_x = 20 cos 30° ≈ 17.3; v_y = 20 sin 30° = 10.", "tools": ["calc"]}, {"kind": "mcq", "text": "A boat heads straight across a river at 4 m/s; the current flows at 3 m/s. Its speed relative to the bank is", "opts": ["7 m/s", "3.5 m/s", "5 m/s", "1 m/s"], "correct": 2, "tag": "", "sol": "Perpendicular velocities: √(4² + 3²) = 5 m/s."}, {"kind": "mcq", "text": "Two displacements of 3 m and 4 m are added. Which resultant is impossible?", "opts": ["7 m", "1 m", "5 m", "8 m"], "correct": 3, "tag": "", "sol": "The resultant lies between 4 − 3 = 1 m and 4 + 3 = 7 m."}, {"kind": "mcq", "text": "What is the horizontal component of a velocity of 10 m/s pointing straight up?", "opts": ["10 m/s", "5 m/s", "7.1 m/s", "0"], "correct": 3, "tag": "", "sol": "cos 90° = 0: a vertical vector has no horizontal component."}, {"kind": "blank", "p": "A hiker walks 5 km north and then 12 km east.", "tag": "", "marks": "", "flat": [{"t": "Distance walked = __B1__ km", "a": {"B1": "17"}}, {"t": "Size of displacement = __B1__ km", "a": {"B1": "13"}}, {"t": "Direction = __B1__° east of north", "a": {"B1": "67.4"}, "expr": "approx"}], "sol": "5 + 12 = 17 km.\n√(5² + 12²) = 13 km.\ntan⁻¹(12 ÷ 5) ≈ 67.4°.", "fig": "<svg class=\"figsvg\" viewBox=\"0 0 260 170\" role=\"img\"><defs><marker id=\"ah\" viewBox=\"0 0 10 10\" refX=\"9\" refY=\"5\" markerWidth=\"7\" markerHeight=\"7\" orient=\"auto\"><path d=\"M0,1 L10,5 L0,9 z\" class=\"ahd\"/></marker><marker id=\"ahs\" viewBox=\"0 0 10 10\" refX=\"1\" refY=\"5\" markerWidth=\"7\" markerHeight=\"7\" orient=\"auto\"><path d=\"M10,1 L0,5 L10,9 z\" class=\"ahd\"/></marker></defs><line style=\"stroke:var(--accent-text);stroke-width:2.2\" x1=\"40.0\" y1=\"140.0\" x2=\"40.0\" y2=\"60.0\" marker-end=\"url(#ah)\"/><text class=\"lb\" x=\"14.0\" y=\"92.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">5 km N</text><line style=\"stroke:var(--success);stroke-width:2.2\" x1=\"40.0\" y1=\"60.0\" x2=\"232.0\" y2=\"60.0\" marker-end=\"url(#ah)\"/><text class=\"lb\" x=\"144.0\" y=\"52.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">12 km E</text><line style=\"stroke:var(--danger);stroke-width:2.2\" x1=\"40.0\" y1=\"140.0\" x2=\"232.0\" y2=\"60.0\" marker-end=\"url(#ah)\"/><text class=\"lb\" x=\"144.0\" y=\"92.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">R</text></svg>", "tools": ["calc"]}, {"kind": "blank", "p": "A ball is kicked at 50 m/s at 37° above the horizontal.", "tag": "", "marks": "", "flat": [{"t": "Horizontal component = __B1__ m/s", "a": {"B1": "39.9"}, "expr": "approx"}, {"t": "Vertical component = __B1__ m/s", "a": {"B1": "30.1"}, "expr": "approx"}], "sol": "50 cos 37° ≈ 39.9 m/s.\n50 sin 37° ≈ 30.1 m/s.", "tools": ["calc"]}]}, {"id": "s11", "label": "1.5.B", "sub": "Motion in two dimensions — LO 1.5.B: describe the motion of an object moving in two dimensions (projectiles).", "slides": [{"kind": "mcq", "text": "A ball rolls off a table. While it falls, its horizontal velocity", "opts": ["decreases", "stays constant", "becomes zero at the floor", "increases"], "correct": 1, "tag": "", "sol": "a_x = 0 for a projectile."}, {"kind": "mcq", "text": "At the highest point of a projectile's path, which is true?", "opts": ["v_y = 0, v_x = 0, a = 0", "v_y = 0, v_x unchanged, a = 0", "v_y = 0, v_x unchanged, a = 10 m/s² down", "both velocities unchanged, a = 10 m/s² down"], "correct": 2, "tag": "", "sol": "Only v_y is zero at the top."}, {"kind": "mcq", "text": "A diver runs horizontally off a cliff at speed v and lands d from the base. At 2v she would land", "opts": ["2d from the base", "d from the base", "√2·d from the base", "4d from the base"], "correct": 0, "tag": "", "sol": "The fall time depends only on the height."}, {"kind": "mcq", "text": "A ball rolls off a 20 m high roof and lands 10 m from the base of the building. How fast did it leave the roof?", "opts": ["10 m/s", "0.5 m/s", "2 m/s", "5 m/s"], "correct": 3, "tag": "", "sol": "t = √(2 × 20 ÷ 10) = 2 s; v = 10 ÷ 2 = 5 m/s.", "fig": "<svg class=\"figsvg\" viewBox=\"0 0 320 200\" role=\"img\"><defs><marker id=\"ah\" viewBox=\"0 0 10 10\" refX=\"9\" refY=\"5\" markerWidth=\"7\" markerHeight=\"7\" orient=\"auto\"><path d=\"M0,1 L10,5 L0,9 z\" class=\"ahd\"/></marker><marker id=\"ahs\" viewBox=\"0 0 10 10\" refX=\"1\" refY=\"5\" markerWidth=\"7\" markerHeight=\"7\" orient=\"auto\"><path d=\"M10,1 L0,5 L10,9 z\" class=\"ahd\"/></marker></defs><line x1=\"4.0\" y1=\"178.0\" x2=\"316\" y2=\"178.0\" style=\"stroke:var(--ink);stroke-width:1.6\"/><rect x=\"4.0\" y=\"51.3\" width=\"20.0\" height=\"126.7\" style=\"fill:var(--gold-soft);stroke:var(--ink);stroke-width:1.2\"/><polyline points=\"24.0,51.3 27.8,51.4 31.6,51.5 35.3,51.7 39.1,51.9 42.9,52.2 46.7,52.6 50.4,53.1 54.2,53.6 58.0,54.2 61.8,54.9 65.6,55.6 69.3,56.4 73.1,57.3 76.9,58.2 80.7,59.2 84.4,60.3 88.2,61.5 92.0,62.7 95.8,64.0 99.6,65.4 103.3,66.8 107.1,68.4 110.9,69.9 114.7,71.6 118.4,73.3 122.2,75.1 126.0,77.0 129.8,78.9 133.6,80.9 137.3,83.0 141.1,85.1 144.9,87.4 148.7,89.7 152.4,92.0 156.2,94.4 160.0,96.9 163.8,99.5 167.6,102.1 171.3,104.9 175.1,107.6 178.9,110.5 182.7,113.4 186.4,116.4 190.2,119.5 194.0,122.6 197.8,125.8 201.6,129.1 205.3,132.4 209.1,135.8 212.9,139.3 216.7,142.8 220.4,146.5 224.2,150.2 228.0,153.9 231.8,157.8 235.6,161.7 239.3,165.7 243.1,169.7 246.9,173.8 250.7,178.0\" style=\"fill:none;stroke:var(--danger);stroke-width:2;stroke-dasharray:5 4\"/><circle cx=\"24.0\" cy=\"51.3\" r=\"4\" style=\"fill:var(--accent-text)\"/><text class=\"lb\" x=\"14.0\" y=\"114.7\" text-anchor=\"middle\" dominant-baseline=\"middle\">20 m</text><text class=\"lb\" x=\"137.3\" y=\"190.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">10 m</text></svg>", "tools": ["calc"]}, {"kind": "mcq", "text": "Two balls are launched at the same speed at 30° and 60°. They land at the same place. Which lands first?", "opts": ["they land together", "the 60° ball", "the 30° ball", "it depends on their masses"], "correct": 2, "tag": "", "sol": "Smaller vertical velocity, shorter flight."}, {"kind": "mcq", "text": "On level ground, which launch angle gives the greatest range?", "opts": ["90°", "60°", "30°", "45°"], "correct": 3, "tag": "", "sol": "R = v² sin 2θ ÷ g is largest at 45°."}, {"kind": "mcq", "text": "A ball passes P on the way up and R on the way down at the same height; Q is the top. How do the speeds compare?", "opts": ["v_P = v_Q = v_R", "v_R < v_Q < v_P", "v_Q < v_P = v_R", "v_P < v_Q < v_R"], "correct": 2, "tag": "", "sol": "Equal heights, equal speeds; least speed at the top."}, {"kind": "mcq", "text": "An arrow is fired horizontally at a target 25 m away and hits 0.20 m below the aim point. How fast was it?", "opts": ["62.5 m/s", "125 m/s", "250 m/s", "12.5 m/s"], "correct": 1, "tag": "", "sol": "t = √(2 × 0.20 ÷ 10) = 0.20 s; v = 25 ÷ 0.20 = 125 m/s.", "tools": ["calc"]}, {"kind": "blank", "p": "A ball is kicked horizontally at 15 m/s off a cliff 45 m high.", "tag": "", "marks": "", "flat": [{"t": "Time to reach the ground = __B1__ s", "a": {"B1": "3"}}, {"t": "Horizontal distance = __B1__ m", "a": {"B1": "45"}}, {"t": "Vertical speed on landing = __B1__ m/s", "a": {"B1": "30"}}, {"t": "Landing speed = __B1__ m/s", "a": {"B1": "33.5"}, "expr": "approx"}], "sol": "45 = 5t², t = 3 s.\n15 × 3 = 45 m.\n10 × 3 = 30 m/s.\n√(15² + 30²) ≈ 33.5 m/s.", "fig": "<svg class=\"figsvg\" viewBox=\"0 0 320 200\" role=\"img\"><defs><marker id=\"ah\" viewBox=\"0 0 10 10\" refX=\"9\" refY=\"5\" markerWidth=\"7\" markerHeight=\"7\" orient=\"auto\"><path d=\"M0,1 L10,5 L0,9 z\" class=\"ahd\"/></marker><marker id=\"ahs\" viewBox=\"0 0 10 10\" refX=\"1\" refY=\"5\" markerWidth=\"7\" markerHeight=\"7\" orient=\"auto\"><path d=\"M10,1 L0,5 L10,9 z\" class=\"ahd\"/></marker></defs><line x1=\"4.0\" y1=\"178.0\" x2=\"316\" y2=\"178.0\" style=\"stroke:var(--ink);stroke-width:1.6\"/><rect x=\"4.0\" y=\"41.2\" width=\"20.0\" height=\"136.8\" style=\"fill:var(--gold-soft);stroke:var(--ink);stroke-width:1.2\"/><polyline points=\"24.0,41.2 28.1,41.2 32.2,41.4 36.2,41.5 40.3,41.8 44.4,42.2 48.5,42.6 52.6,43.1 56.6,43.6 60.7,44.3 64.8,45.0 68.9,45.8 73.0,46.7 77.0,47.6 81.1,48.6 85.2,49.8 89.3,50.9 93.4,52.2 97.4,53.5 101.5,54.9 105.6,56.4 109.7,58.0 113.8,59.6 117.8,61.3 121.9,63.1 126.0,65.0 130.1,66.9 134.2,68.9 138.2,71.0 142.3,73.2 146.4,75.4 150.5,77.7 154.6,80.1 158.6,82.6 162.7,85.1 166.8,87.8 170.9,90.4 175.0,93.2 179.0,96.1 183.1,99.0 187.2,102.0 191.3,105.1 195.4,108.2 199.4,111.5 203.5,114.8 207.6,118.2 211.7,121.6 215.8,125.1 219.8,128.8 223.9,132.4 228.0,136.2 232.1,140.0 236.2,144.0 240.2,147.9 244.3,152.0 248.4,156.2 252.5,160.4 256.6,164.7 260.6,169.0 264.7,173.5 268.8,178.0\" style=\"fill:none;stroke:var(--danger);stroke-width:2;stroke-dasharray:5 4\"/><circle cx=\"24.0\" cy=\"41.2\" r=\"4\" style=\"fill:var(--accent-text)\"/><text class=\"lb\" x=\"14.0\" y=\"109.6\" text-anchor=\"middle\" dominant-baseline=\"middle\">45 m</text><text class=\"lb\" x=\"146.4\" y=\"190.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">?</text></svg>", "tools": ["calc", "desmos"], "desmos": ["y=45-5\\left(\\frac{x}{15}\\right)^2\\{0\\le x\\le45\\}"]}, {"kind": "blank", "p": "A ball is launched at 25 m/s at 30° above level ground.", "tag": "", "marks": "", "flat": [{"t": "v_x = __B1__ m/s", "a": {"B1": "21.7"}, "expr": "approx"}, {"t": "Initial v_y = __B1__ m/s", "a": {"B1": "12.5"}}, {"t": "Time of flight = __B1__ s", "a": {"B1": "2.5"}}, {"t": "Range = __B1__ m", "a": {"B1": "54.1"}, "expr": "approx"}, {"t": "Maximum height = __B1__ m", "a": {"B1": "7.81"}, "expr": "approx"}], "sol": "25 cos 30° ≈ 21.7 m/s.\n25 sin 30° = 12.5 m/s.\n2 × 12.5 ÷ 10 = 2.5 s.\n21.65 × 2.5 ≈ 54.1 m.\n12.5² ÷ 20 ≈ 7.81 m.", "tools": ["calc", "desmos"], "desmos": ["y=0.57735x-\\frac{5x^2}{468.75}\\{0\\le x\\le54.13\\}"]}, {"kind": "blank", "p": "The same ball is now launched at 25 m/s at 60°.", "tag": "", "marks": "", "flat": [{"t": "Range = __B1__ m", "a": {"B1": "54.1"}, "expr": "approx"}, {"t": "Maximum height = __B1__ m", "a": {"B1": "23.4"}, "expr": "approx"}, {"t": "Compared with 30°, it stays in the air __B1__ (longer / shorter).", "a": {"B1": "longer"}, "expr": "words"}], "sol": "sin 120° = sin 60°: same range ≈ 54.1 m.\n(25 sin 60°)² ÷ 20 ≈ 23.4 m.\nLarger v_y: about 4.33 s in the air.", "tools": ["calc", "desmos"], "desmos": ["y=1.7321x-\\frac{5x^2}{156.25}\\{0\\le x\\le54.13\\}", "y=0.57735x-\\frac{5x^2}{468.75}\\{0\\le x\\le54.13\\}"]}, {"kind": "blank", "p": "A plane flying level at 50 m/s at a height of 180 m drops a relief package.", "tag": "", "marks": "", "flat": [{"t": "Fall time = __B1__ s", "a": {"B1": "6"}}, {"t": "It lands __B1__ m ahead of the drop point.", "a": {"B1": "300"}}, {"t": "Seen from the plane, the package stays directly __B1__ it.", "a": {"B1": "below"}, "expr": "words", "accept": ["under", "beneath", "underneath"]}], "sol": "180 = 5t², t = 6 s.\n50 × 6 = 300 m.\nIt keeps the plane's horizontal velocity.", "tools": ["calc"]}]}, {"id": "s12", "label": "Test A", "sub": "Test A — Knowing and understanding", "slides": [{"kind": "mcq", "text": "A rocket accelerating upward at 12 m/s² releases a package. Immediately after release, the package's acceleration is", "opts": ["2 m/s² upward", "zero", "10 m/s² downward", "12 m/s² upward"], "correct": 2, "tag": "", "sol": "Only gravity acts on the package once released. [1.3.A]"}, {"kind": "mcq", "text": "A scooter goes from rest to 24 m/s in 8.0 s. Its acceleration is", "opts": ["192 m/s²", "16 m/s²", "3.0 m/s²", "0.33 m/s²"], "correct": 2, "tag": "", "sol": "24 ÷ 8 = 3.0 m/s². [1.2.B]", "tools": ["calc"]}, {"kind": "mcq", "text": "A stone is dropped from 80 m. How long does it take to reach the ground?", "opts": ["2.0 s", "16 s", "4.0 s", "8.0 s"], "correct": 2, "tag": "", "sol": "t = √(2 × 80 ÷ 10) = 4.0 s. [1.3.A]", "tools": ["calc"]}, {"kind": "mcq", "text": "The slope of a velocity–time graph gives", "opts": ["distance", "displacement", "velocity", "acceleration"], "correct": 3, "tag": "", "sol": "Δv ÷ Δt. [1.3.A]"}, {"kind": "mcq", "text": "Which graph shows the vertical velocity of a projectile against time (up positive)?", "opts": ["a horizontal line", "a straight line sloping up", "a parabola", "a straight line sloping down, crossing zero at the top"], "correct": 3, "tag": "", "sol": "v_y = v₀ sin θ − gt. [1.5.B]"}, {"kind": "mcq", "text": "A passenger walks at 1.2 m/s towards the back of a train moving at 25 m/s. Her speed relative to the track is", "opts": ["23.8 m/s", "25 m/s", "26.2 m/s", "1.2 m/s"], "correct": 0, "tag": "", "sol": "25 − 1.2 = 23.8 m/s. [1.4.B]"}, {"kind": "mcq", "text": "What is the resultant of 6 m east and 8 m south?", "opts": ["10 m", "14 m", "2 m", "48 m"], "correct": 0, "tag": "", "sol": "√(6² + 8²) = 10 m. [1.5.A]"}, {"kind": "blank", "p": "A car moving at 18 m/s brakes steadily to rest in 3.6 s.", "tag": "", "marks": "", "flat": [{"t": "Acceleration = __B1__ m/s²", "a": {"B1": "-5"}}, {"t": "Braking distance = __B1__ m", "a": {"B1": "32.4"}, "expr": "approx"}], "sol": "(0 − 18) ÷ 3.6 = −5 m/s².\n½(18)(3.6) = 32.4 m.", "tools": ["calc"]}, {"kind": "blank", "p": "A marble rolls off a 1.25 m high table at 8.0 m/s.", "tag": "", "marks": "", "flat": [{"t": "Fall time = __B1__ s", "a": {"B1": "0.5"}}, {"t": "It lands __B1__ m from the table.", "a": {"B1": "4"}}], "sol": "1.25 = 5t², t = 0.5 s.\n8.0 × 0.5 = 4.0 m.", "tools": ["calc", "desmos"], "desmos": ["y=1.25-5\\left(\\frac{x}{8}\\right)^2\\{0\\le x\\le4\\}"]}, {"kind": "blank", "p": "Use the velocity–time graph.", "tag": "", "marks": "", "flat": [{"t": "Displacement in 10 s = __B1__ m", "a": {"B1": "100"}}, {"t": "Average velocity = __B1__ m/s", "a": {"B1": "10"}}, {"t": "Acceleration = __B1__ m/s²", "a": {"B1": "2"}}], "sol": "½ × 10 × 20 = 100 m.\n100 ÷ 10 = 10 m/s.\n20 ÷ 10 = 2 m/s².", "fig": "<svg class=\"figsvg\" viewBox=\"0 0 320 230\" role=\"img\"><defs><marker id=\"ah\" viewBox=\"0 0 10 10\" refX=\"9\" refY=\"5\" markerWidth=\"7\" markerHeight=\"7\" orient=\"auto\"><path d=\"M0,1 L10,5 L0,9 z\" class=\"ahd\"/></marker><marker id=\"ahs\" viewBox=\"0 0 10 10\" refX=\"1\" refY=\"5\" markerWidth=\"7\" markerHeight=\"7\" orient=\"auto\"><path d=\"M10,1 L0,5 L10,9 z\" class=\"ahd\"/></marker></defs><line style=\"stroke:var(--rule)\" x1=\"46.0\" y1=\"196\" x2=\"46.0\" y2=\"18\"/><text class=\"po\" x=\"46.0\" y=\"209.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">0</text><line style=\"stroke:var(--rule)\" x1=\"71.4\" y1=\"196\" x2=\"71.4\" y2=\"18\"/><text class=\"po\" x=\"71.4\" y=\"209.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">1</text><line style=\"stroke:var(--rule)\" x1=\"96.8\" y1=\"196\" x2=\"96.8\" y2=\"18\"/><text class=\"po\" x=\"96.8\" y=\"209.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">2</text><line style=\"stroke:var(--rule)\" x1=\"122.2\" y1=\"196\" x2=\"122.2\" y2=\"18\"/><text class=\"po\" x=\"122.2\" y=\"209.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">3</text><line style=\"stroke:var(--rule)\" x1=\"147.6\" y1=\"196\" x2=\"147.6\" y2=\"18\"/><text class=\"po\" x=\"147.6\" y=\"209.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">4</text><line style=\"stroke:var(--rule)\" x1=\"173.0\" y1=\"196\" x2=\"173.0\" y2=\"18\"/><text class=\"po\" x=\"173.0\" y=\"209.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">5</text><line style=\"stroke:var(--rule)\" x1=\"198.4\" y1=\"196\" x2=\"198.4\" y2=\"18\"/><text class=\"po\" x=\"198.4\" y=\"209.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">6</text><line style=\"stroke:var(--rule)\" x1=\"223.8\" y1=\"196\" x2=\"223.8\" y2=\"18\"/><text class=\"po\" x=\"223.8\" y=\"209.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">7</text><line style=\"stroke:var(--rule)\" x1=\"249.2\" y1=\"196\" x2=\"249.2\" y2=\"18\"/><text class=\"po\" x=\"249.2\" y=\"209.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">8</text><line style=\"stroke:var(--rule)\" x1=\"274.6\" y1=\"196\" x2=\"274.6\" y2=\"18\"/><text class=\"po\" x=\"274.6\" y=\"209.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">9</text><line style=\"stroke:var(--rule)\" x1=\"300.0\" y1=\"196\" x2=\"300.0\" y2=\"18\"/><text class=\"po\" x=\"300.0\" y=\"209.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">10</text><line style=\"stroke:var(--rule)\" x1=\"46\" y1=\"196.0\" x2=\"300\" y2=\"196.0\"/><text class=\"po\" x=\"40.0\" y=\"196.0\" text-anchor=\"end\" dominant-baseline=\"middle\">0</text><line style=\"stroke:var(--rule)\" x1=\"46\" y1=\"151.5\" x2=\"300\" y2=\"151.5\"/><text class=\"po\" x=\"40.0\" y=\"151.5\" text-anchor=\"end\" dominant-baseline=\"middle\">5</text><line style=\"stroke:var(--rule)\" x1=\"46\" y1=\"107.0\" x2=\"300\" y2=\"107.0\"/><text class=\"po\" x=\"40.0\" y=\"107.0\" text-anchor=\"end\" dominant-baseline=\"middle\">10</text><line style=\"stroke:var(--rule)\" x1=\"46\" y1=\"62.5\" x2=\"300\" y2=\"62.5\"/><text class=\"po\" x=\"40.0\" y=\"62.5\" text-anchor=\"end\" dominant-baseline=\"middle\">15</text><line style=\"stroke:var(--rule)\" x1=\"46\" y1=\"18.0\" x2=\"300\" y2=\"18.0\"/><text class=\"po\" x=\"40.0\" y=\"18.0\" text-anchor=\"end\" dominant-baseline=\"middle\">20</text><line class=\"ln\" x1=\"46.0\" y1=\"196.0\" x2=\"308.0\" y2=\"196.0\" marker-end=\"url(#ah)\"/><line class=\"ln\" x1=\"46.0\" y1=\"196.0\" x2=\"46.0\" y2=\"10.0\" marker-end=\"url(#ah)\"/><text class=\"lb\" x=\"300.0\" y=\"188.0\" text-anchor=\"end\" dominant-baseline=\"middle\">t (s)</text><text class=\"lb\" x=\"52.0\" y=\"12.0\" text-anchor=\"start\" dominant-baseline=\"middle\">v (m/s)</text><polyline fill=\"none\" style=\"stroke:var(--danger);stroke-width:2.2\" points=\"46.0,196.0 300.0,18.0\"/><circle cx=\"46.0\" cy=\"196.0\" r=\"3\" style=\"fill:var(--danger)\"/><circle cx=\"300.0\" cy=\"18.0\" r=\"3\" style=\"fill:var(--danger)\"/></svg>"}]}, {"id": "s13", "label": "Test B", "sub": "Test B — Investigating patterns", "slides": [{"kind": "blank", "p": "A ball is dropped and timed.\nt (s): 0.5, 1.0, 1.5, 2.0   →   d (m): 1.25, 5, 11.25, 20", "tag": "", "marks": "", "flat": [{"t": "d ÷ t² for every row = __B1__", "a": {"B1": "5"}}, {"t": "So d = __B1__ (in terms of t)", "a": {"B1": "5t^2"}, "expr": true}, {"t": "Predicted d at t = 3.0 s = __B1__ m", "a": {"B1": "45"}}], "sol": "1.25 ÷ 0.25 = 5 … 20 ÷ 4 = 5.\nd = 5t² (= ½gt²).\n5 × 9 = 45 m.", "tools": ["calc", "desmos"], "desmos": [{"type": "table", "columns": [{"latex": "x_1", "values": ["0.5", "1", "1.5", "2"]}, {"latex": "y_1", "values": ["1.25", "5", "11.25", "20"]}]}, "y_1\\sim ax_1^2"]}, {"kind": "blank", "p": "Stopping distances of a car with the same brakes:\nv (m/s): 10, 20, 30   →   d (m): 5, 20, 45", "tag": "", "marks": "", "flat": [{"t": "When v doubles, d is multiplied by __B1__", "a": {"B1": "4"}}, {"t": "A rule is d = __B1__ × v²", "a": {"B1": "0.05"}, "accept": ["1/20"]}, {"t": "Predicted stopping distance at 40 m/s = __B1__ m", "a": {"B1": "80"}}], "sol": "20 ÷ 5 = 4.\n5 ÷ 100 = 0.05.\n0.05 × 1600 = 80 m.", "tools": ["calc"]}, {"kind": "mcq", "text": "Ranges of a ball launched at 20 m/s: 15° → 20 m, 30° → 34.6 m, 45° → 40 m, 60° → 34.6 m, 75° → 20 m. Which conclusion fits?", "opts": ["The range does not depend on the angle", "The range is greatest at 75°", "Angles adding to 90° give the same range, and 45° gives the most", "The range doubles when the angle doubles"], "correct": 2, "tag": "", "sol": "Complementary angles give equal ranges; the maximum is at 45°.", "tools": ["desmos"], "desmos": ["y=\\frac{400\\sin(2x)}{10}"]}, {"kind": "blank", "p": "A cart starts from rest with a = 2 m/s². Find the distance covered in each second.", "tag": "", "marks": "", "flat": [{"t": "1st, 2nd, 3rd, 4th seconds (m): __B1__", "a": {"B1": "1, 3, 5, 7"}, "expr": "dlist"}, {"t": "Each second's distance is __B1__ m more than the last.", "a": {"B1": "2"}}, {"t": "Distance in the 10th second = __B1__ m", "a": {"B1": "19"}}], "sol": "x = t²: 1, 4, 9, 16.\nThey increase by 2 m.\n100 − 81 = 19 m."}, {"kind": "mcq", "text": "Maximum heights of balls thrown up: 10 m/s → 5 m, 20 m/s → 20 m, 30 m/s → 45 m. Height is proportional to", "opts": ["the square of the launch speed", "the cube of the launch speed", "the square root of the launch speed", "the launch speed"], "correct": 0, "tag": "", "sol": "×2 speed → ×4 height; ×3 → ×9."}, {"kind": "mcq", "text": "A ball rebounds to half its previous height each bounce. The time between the 1st and 2nd bounces is 1.0 s. The time between the 2nd and 3rd is", "opts": ["1.0 s", "0.25 s", "0.50 s", "0.71 s"], "correct": 3, "tag": "", "sol": "Time in the air ∝ √height: × √½ ≈ 0.71."}, {"kind": "blank", "p": "Launch speed 15 m/s, horizontal throws from different heights:\nh (m): 5, 20, 45", "tag": "", "marks": "", "flat": [{"t": "Fall times (s): __B1__", "a": {"B1": "1, 2, 3"}, "expr": "dlist"}, {"t": "Ranges (m): __B1__", "a": {"B1": "15, 30, 45"}, "expr": "dlist"}, {"t": "To double the range, multiply the height by __B1__", "a": {"B1": "4"}}], "sol": "t = √(h/5).\n15t.\nRange ∝ √h.", "tools": ["calc"]}]}, {"id": "s14", "label": "Test C", "sub": "Test C — Communicating", "slides": [{"kind": "mcq", "text": "Which statement is correct?", "opts": ["Speed can be negative", "Velocity includes a direction; speed does not", "Velocity is distance divided by time", "Speed and velocity always have the same value"], "correct": 1, "tag": "", "sol": "Speed is a scalar; velocity is a vector (displacement ÷ time)."}, {"kind": "mcq", "text": "Asked for the acceleration of a dropped ball, a student writes “a = 10”. What is the best improvement?", "opts": ["a = −10", "a = 10 m/s² downward", "a = 10.0", "a = 10 m/s"], "correct": 1, "tag": "", "sol": "A complete answer gives the value, the correct unit (m/s²) and, for a vector, the direction."}, {"kind": "mcq", "text": "Taking up as positive, which pair describes a ball at the top of its flight?", "opts": ["v = −10 m/s, a = 0", "v = 0, a = −10 m/s²", "v = 0, a = +10 m/s²", "v = 0, a = 0"], "correct": 1, "tag": "", "sol": "At the top the velocity is zero; the acceleration is still 10 m/s² downward, which is negative with up positive."}, {"kind": "mcq", "text": "A student measures 12.0 m in 3.456 s. How should the average speed be reported?", "opts": ["3.5 m/s", "3 m/s", "3.4722 m/s", "3.47 m/s"], "correct": 3, "tag": "", "sol": "12.0 has 3 significant figures, so give 3: 12.0 ÷ 3.456 = 3.472… ≈ 3.47 m/s."}, {"kind": "mcq", "text": "Which describes an object speeding up while moving in the negative direction?", "opts": ["a v–t line below the axis, moving towards zero", "a v–t line below the axis, getting more negative", "a v–t line above the axis, getting larger", "a horizontal v–t line below the axis"], "correct": 1, "tag": "", "sol": "Negative v growing in size: the line is below the axis and moves further from it."}, {"kind": "mcq", "text": "Priya writes: “From rest at 2 m/s² for 4 s, Δx = v₀t + at² = 0 + 2 × 16 = 32 m.” What is wrong?", "opts": ["v₀ should be 2 m/s", "She should have used v = v₀ + at", "Nothing is wrong", "The equation needs ½at², so Δx = 16 m"], "correct": 3, "tag": "", "sol": "Δx = v₀t + ½at² = ½ × 2 × 16 = 16 m."}, {"kind": "mcq", "text": "Which is the clearest way to show how a car's speed changes as it stops at a red light and moves off again?", "opts": ["a pie chart", "a single average speed", "a list of positions", "a velocity–time graph"], "correct": 3, "tag": "", "sol": "A v–t graph shows the slowing down, the stop and the speeding up, and its slope gives the accelerations."}, {"kind": "mcq", "text": "A student says: “At the top of its path a projectile has zero velocity.” Which correction is best?", "opts": ["Only the vertical velocity is zero; the horizontal velocity is unchanged", "It is correct as written", "The acceleration is zero there", "Both velocity and acceleration are zero"], "correct": 0, "tag": "", "sol": "v_x stays constant throughout; only v_y is zero at the top."}, {"kind": "blank", "p": "Complete the explanations with one word.", "tag": "", "marks": "", "flat": [{"t": "The slope of a position–time graph gives the __B1__.", "a": {"B1": "velocity"}, "expr": "words"}, {"t": "The area under a velocity–time graph gives the __B1__.", "a": {"B1": "displacement"}, "expr": "words"}, {"t": "A quantity with size and direction is called a __B1__.", "a": {"B1": "vector"}, "expr": "words"}], "sol": "Δx/Δt = velocity.\nv × t = displacement.\nVector (a scalar has size only)."}, {"kind": "blank", "p": "Rohan's answer to “how far does a car travel from rest at 3 m/s² in 5 s?” reads “37.5”.", "tag": "", "marks": "", "flat": [{"t": "His number is correct: ½ × 3 × 5² = __B1__", "a": {"B1": "37.5"}}, {"t": "He should add the unit, __B1__.", "a": {"B1": "metres"}, "expr": "words", "accept": ["m", "meters", "metre", "meter"]}, {"t": "A better final line is: “The car travels 37.5 m in its __B1__ direction.” (forward / backward)", "a": {"B1": "forward"}, "expr": "words", "accept": ["forwards", "positive", "original", "initial"]}], "sol": "½ × 3 × 25 = 37.5.\nDistance is in metres.\nState the answer in a sentence with unit (and direction for displacement)."}]}, {"id": "s15", "label": "Test D", "sub": "Test D — Applying physics in real-life contexts", "slides": [{"kind": "mcq", "text": "A metro train goes from rest to 72 km/h in 40 s. What is its average acceleration?", "opts": ["0.5 m/s²", "2 m/s²", "0.05 m/s²", "1.8 m/s²"], "correct": 0, "tag": "", "sol": "72 km/h = 20 m/s; 20 ÷ 40 = 0.5 m/s².", "tools": ["calc"]}, {"kind": "mcq", "text": "A fielder throws a cricket ball at 25 m/s at 40° to the keeper 60 m away (same height). Does it reach him without bouncing?", "opts": ["No, its range is about 31 m", "No, its range is about 48 m", "Yes, its range is about 125 m", "Yes, its range is about 61.6 m"], "correct": 3, "tag": "", "sol": "R = 625 sin 80° ÷ 10 ≈ 61.6 m > 60 m.", "tools": ["calc", "desmos"], "desmos": ["y=\\tan(40)x-\\frac{10x^2}{2\\cdot625\\cos(40)^2}"]}, {"kind": "mcq", "text": "A student calculates that a ball dropped from 5 m hits the floor at 100 m/s. Is this reasonable?", "opts": ["Yes: heavy balls fall faster", "Yes: 10 × 10 = 100", "No: it would be 50 m/s", "No: v = √(2 × 10 × 5) = 10 m/s"], "correct": 3, "tag": "", "sol": "100 m/s is 360 km/h — far too fast. v² = 2gh = 100, v = 10 m/s: the square root was forgotten.", "tools": ["calc"]}, {"kind": "mcq", "text": "On a highway a car at 28 m/s is 120 m behind a bus at 22 m/s, both heading the same way. How long until the car draws level?", "opts": ["4.3 s", "20 s", "2.4 s", "6 s"], "correct": 1, "tag": "", "sol": "Closing speed 28 − 22 = 6 m/s; 120 ÷ 6 = 20 s."}, {"kind": "mcq", "text": "A batter hits a cricket ball straight up and catches it 4.0 s later at the same height. How high did it rise?", "opts": ["40 m", "20 m", "80 m", "10 m"], "correct": 1, "tag": "", "sol": "2.0 s up: h = ½ × 10 × 2.0² = 20 m.", "tools": ["calc"]}, {"kind": "blank", "p": "A driver moving at 20 m/s sees an obstacle 45 m ahead. Her reaction time is 0.80 s; then she brakes at 8.0 m/s².", "tag": "", "marks": "", "flat": [{"t": "Reaction distance = __B1__ m", "a": {"B1": "16"}}, {"t": "Braking distance = __B1__ m", "a": {"B1": "25"}}, {"t": "Total stopping distance = __B1__ m", "a": {"B1": "41"}}, {"t": "Does she stop in time? __B1__", "a": {"B1": "yes"}, "expr": "words", "accept": ["y"]}], "sol": "20 × 0.80 = 16 m.\n400 ÷ 16 = 25 m.\n41 m.\n41 < 45: yes.", "tools": ["calc"]}, {"kind": "blank", "p": "A helicopter flying level at 45 m/s, 125 m up, drops food packets for a flood-hit village.", "tag": "", "marks": "", "flat": [{"t": "Fall time = __B1__ s", "a": {"B1": "5"}}, {"t": "Release the packet __B1__ m before the target.", "a": {"B1": "225"}}], "sol": "125 = 5t², t = 5 s.\n45 × 5 = 225 m.", "tools": ["calc", "desmos"], "desmos": ["y=125-5\\left(\\frac{x}{45}\\right)^2\\{0\\le x\\le225\\}"]}, {"kind": "blank", "p": "A goalkeeper kicks a football from the ground at 22 m/s at 35°. The halfway line is 50 m away.", "tag": "", "marks": "", "flat": [{"t": "Time in the air = __B1__ s", "a": {"B1": "2.52"}, "expr": "approx"}, {"t": "Range = __B1__ m", "a": {"B1": "45.5"}, "expr": "approx"}, {"t": "Does it land beyond the halfway line? __B1__", "a": {"B1": "no"}, "expr": "words", "accept": ["n"]}], "sol": "2 × 22 sin 35° ÷ 10 ≈ 2.52 s.\n22 cos 35° × 2.52 ≈ 45.5 m.\n45.5 < 50: no.", "tools": ["calc", "desmos"], "desmos": ["y=\\tan(35)x-\\frac{10x^2}{2\\cdot484\\cos(35)^2}"]}, {"kind": "blank", "p": "A lift rises from rest at 1.5 m/s² for 2.0 s, moves at constant speed for 6.0 s, then slows uniformly to rest in 2.0 s.", "tag": "", "marks": "", "flat": [{"t": "Top speed = __B1__ m/s", "a": {"B1": "3"}}, {"t": "Total height climbed = __B1__ m", "a": {"B1": "24"}}, {"t": "The fastest part is the __B1__ stage (first / middle / last).", "a": {"B1": "middle"}, "expr": "words"}], "sol": "1.5 × 2 = 3 m/s.\n3 + 18 + 3 = 24 m.\nConstant 3 m/s in the middle.", "tools": ["calc", "desmos"], "desmos": ["y=1.5x\\{0\\le x\\le2\\}", "y=3\\{2\\le x\\le8\\}", "y=3-1.5(x-8)\\{8\\le x\\le10\\}"]}]}];
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
var SHEET_KEY='sopaan-ap1-ch1';
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
  var h='<div class="rec-card"><h2>'+esc(student.name)+'’s record</h2><p class="rec-empty" style="margin:0 0 12px;">Roll '+esc(student.roll)+' · Kinematics</p>';
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
