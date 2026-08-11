[index.html](https://github.com/user-attachments/files/30922078/index.html)
<!doctype html>
<html lang="ko">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>수학과학 미션 파일럿</title>
  <style>
    :root{
      --bg:#0f172a; --card:#111827; --soft:#1f2937; --line:#334155;
      --text:#f8fafc; --muted:#cbd5e1; --accent:#38bdf8; --good:#22c55e; --bad:#fb7185;
    }
    *{box-sizing:border-box}
    body{margin:0;font-family:system-ui,-apple-system,"Pretendard","Noto Sans KR",sans-serif;background:
      radial-gradient(circle at top,#1e293b 0,#0f172a 45%,#020617 100%);color:var(--text);min-height:100vh}
    .wrap{max-width:560px;margin:0 auto;padding:24px 18px 40px}
    .brand{font-size:13px;letter-spacing:.12em;color:#7dd3fc;font-weight:800;margin-bottom:16px}
    .card{background:rgba(17,24,39,.92);border:1px solid var(--line);border-radius:24px;padding:24px;box-shadow:0 20px 50px rgba(0,0,0,.3)}
    h1{font-size:30px;line-height:1.22;margin:0 0 12px}
    h2{font-size:24px;margin:0 0 10px}
    p{line-height:1.7;color:var(--muted)}
    .tag{display:inline-block;padding:7px 10px;border-radius:999px;background:#082f49;color:#bae6fd;font-size:12px;font-weight:700;margin-bottom:14px}
    .progress{height:8px;background:#1e293b;border-radius:999px;overflow:hidden;margin:4px 0 18px}
    .bar{height:100%;width:0;background:linear-gradient(90deg,#38bdf8,#a78bfa);transition:.35s}
    .mission{display:none}
    .mission.active{display:block}
    .question{background:#0b1220;border:1px solid #273449;border-radius:18px;padding:18px;margin:18px 0}
    input{width:100%;padding:14px 15px;border-radius:14px;border:1px solid #475569;background:#020617;color:white;font-size:16px;outline:none}
    input:focus{border-color:var(--accent)}
    button{width:100%;padding:14px 16px;border:0;border-radius:14px;background:var(--accent);color:#082f49;font-size:16px;font-weight:900;cursor:pointer;margin-top:10px}
    button.secondary{background:#1e293b;color:#e2e8f0;border:1px solid #475569}
    .msg{min-height:26px;margin-top:10px;font-weight:800}
    .good{color:#86efac}.bad{color:#fda4af}
    .hint{display:none;background:#172554;color:#dbeafe;padding:12px 14px;border-radius:14px;margin-top:10px;line-height:1.5}
    .code{font-size:34px;letter-spacing:.18em;font-weight:1000;text-align:center;padding:18px;border-radius:18px;background:#052e16;color:#bbf7d0;margin:18px 0}
    .mini{font-size:13px;color:#94a3b8}
  </style>
</head>
<body>
<div class="wrap">
  <div class="brand">GANGSEO · YANGCHEON  |  PILOT TEST</div>
  <div class="card">
    <div class="progress"><div class="bar" id="bar"></div></div>

    <section class="mission active" id="m0">
      <span class="tag">웹 미션 파일럿</span>
      <h1>사라진 연구코드를 찾아라</h1>
      <p>이 페이지는 실제 프로그램 제작 가능성을 확인하기 위한 간이 테스트입니다. 휴대폰에서 문제를 풀고, 정답을 맞히면 다음 미션으로 넘어갑니다.</p>
      <button onclick="go(1)">미션 시작하기</button>
      <p class="mini">※ 서버 없이 작동하는 단일 HTML 파일입니다.</p>
    </section>

    <section class="mission" id="m1">
      <span class="tag">MISSION 1 · 규칙 찾기</span>
      <h2>다음 숫자는?</h2>
      <div class="question">
        <p style="font-size:22px;color:white;text-align:center;font-weight:900">2 → 4 → 8 → 16 → ?</p>
      </div>
      <input id="a1" inputmode="numeric" placeholder="정답 입력">
      <button onclick="check(1,'32')">정답 확인</button>
      <button class="secondary" onclick="hint(1)">힌트 보기</button>
      <div class="hint" id="h1">앞의 수에 같은 수를 곱하고 있습니다.</div>
      <div class="msg" id="msg1"></div>
    </section>

    <section class="mission" id="m2">
      <span class="tag">MISSION 2 · 수학 추리</span>
      <h2>비밀번호의 두 번째 숫자</h2>
      <div class="question">
        <p>정사각형의 한 변이 6cm입니다. 이 정사각형의 넓이는 몇 cm²일까요?</p>
      </div>
      <input id="a2" inputmode="numeric" placeholder="숫자만 입력">
      <button onclick="check(2,'36')">정답 확인</button>
      <button class="secondary" onclick="hint(2)">힌트 보기</button>
      <div class="hint" id="h2">정사각형의 넓이 = 한 변 × 한 변</div>
      <div class="msg" id="msg2"></div>
    </section>

    <section class="mission" id="m3">
      <span class="tag">MISSION 3 · 암호 해독</span>
      <h2>마지막 단서를 해독하라</h2>
      <div class="question">
        <p>A=1, B=2, C=3 … 으로 대응할 때 <b style="color:white">3-15-4-5</b>가 뜻하는 영어 단어는?</p>
      </div>
      <input id="a3" placeholder="영어 단어 입력">
      <button onclick="check(3,'CODE')">정답 확인</button>
      <button class="secondary" onclick="hint(3)">힌트 보기</button>
      <div class="hint" id="h3">3=C, 15=O, 4=D, 5=E</div>
      <div class="msg" id="msg3"></div>
    </section>

    <section class="mission" id="m4">
      <span class="tag">MISSION COMPLETE</span>
      <h1>파일럿 테스트 성공!</h1>
      <p>정답 판정, 단계별 화면 이동, 진행률, 힌트 기능이 모두 정상 작동했습니다.</p>
      <div class="code">GYC-826</div>
      <p>실제 프로그램에서는 이 부분을 최종 인증번호, 완주 화면, 기념사진 안내 등으로 바꿀 수 있습니다.</p>
      <button class="secondary" onclick="restart()">처음부터 다시 하기</button>
    </section>
  </div>
</div>

<script>
let current=0;
function show(n){
  document.querySelectorAll('.mission').forEach(el=>el.classList.remove('active'));
  document.getElementById('m'+n).classList.add('active');
  current=n;
  document.getElementById('bar').style.width=(n/4*100)+'%';
  window.scrollTo({top:0,behavior:'smooth'});
}
function go(n){show(n)}
function norm(v){return v.trim().toUpperCase().replace(/\s+/g,'')}
function check(n,answer){
  const input=document.getElementById('a'+n);
  const msg=document.getElementById('msg'+n);
  if(norm(input.value)===norm(answer)){
    msg.className='msg good';
    msg.textContent='정답입니다! 다음 미션으로 이동합니다.';
    setTimeout(()=>show(n+1),600);
  }else{
    msg.className='msg bad';
    msg.textContent='아쉽습니다. 다시 한 번 확인해보세요.';
  }
}
function hint(n){
  const el=document.getElementById('h'+n);
  el.style.display=el.style.display==='block'?'none':'block';
}
function restart(){
  ['a1','a2','a3'].forEach(id=>document.getElementById(id).value='');
  ['msg1','msg2','msg3'].forEach(id=>document.getElementById(id).textContent='');
  ['h1','h2','h3'].forEach(id=>document.getElementById(id).style.display='none');
  show(0);
}
</script>
</body>
</html>
