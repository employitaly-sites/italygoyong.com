# 견적 받기

> 이탈리아 직원 채용 견적을 요청하세요. 간단한 3단계, 영업일 1일 내 회신.


<section> <span class="eyebrow">견적 받기</span> <h1 id="tell-us-who-you-want-to-hire">어떤 인재를 채용하실지 알려주세요</h1> <p class="lede">간단한 3단계입니다. 영업일 1일 내에 전체 비용과 계약 개요를 보내드립니다. 원화 또는 USD 견적을 받으실 수 있습니다.</p> </section> <section> <form id="lead" class="panel" style="display:grid;gap:18px;max-width:640px" novalidate> <p id="stepinfo" class="tag" style="justify-self:start">1/3단계</p> <fieldset data-step="1" style="border:0;padding:0;margin:0;display:grid;gap:14px"> <label for="email">회사 이메일<input id="email" type="email" autocomplete="email" required></label> <label for="company">회사명<input id="company" autocomplete="organization"></label> </fieldset> <fieldset data-step="2" hidden style="border:0;padding:0;margin:0;display:grid;gap:14px"> <label for="service">필요한 서비스<select id="service"><option>Employer of Record (고용대행)</option><option>급여 아웃소싱 (이탈리아 법인 보유)</option><option>취업 비자 / 블루카드 (한국 인력 등)</option><option>채용</option></select></label> <label for="count">이탈리아 채용 인원<input id="count" type="number" min="1" value="1"></label> <label for="city">도시 또는 지역<input id="city" placeholder="밀라노, 로마, 원격…"></label> <label for="salary">예정 세전 연봉 (EUR)<input id="salary" type="number" step="1000"></label> </fieldset> <fieldset data-step="3" hidden style="border:0;padding:0;margin:0;display:grid;gap:14px"> <label for="name">성함<input id="name" autocomplete="name"></label> <label for="start">희망 입사일<input id="start" type="date"></label> <label for="notes">기타 문의<textarea id="notes" rows="4"></textarea></label> <label style="display:flex;gap:10px;align-items:flex-start;font-weight:400"><input id="consent" type="checkbox" style="width:auto;margin-top:5px">이 문의에 답하기 위해 이탈리아 고용이 제 개인정보를 처리하는 데 동의합니다(개인정보 처리방침).</label> </fieldset> <p id="msg" role="status" style="margin:0;color:var(--accent)"></p> <div class="cta"><button type="button" class="btn ghost" id="back" hidden>이전</button><button type="submit" class="btn" id="next">계속</button></div> </form> </section> <script>
// Il passo 1 salva subito l'email (lead abbandonato recuperabile dal nurturing). Endpoint del worker: /api/lead.
const f = document.getElementById('lead'); let step = 1;
const sets = [...f.querySelectorAll('fieldset')];
const data = () => Object.fromEntries([...f.querySelectorAll('input,select,textarea')].map(e => [e.id, e.type === 'checkbox' ? e.checked : e.value]));
async function save(final){ try { await fetch('/api/lead', {method:'POST', headers:{'Content-Type':'application/json'}, body: JSON.stringify({...data(), step, final, brand:'italygoyong'})}); } catch(e){} }
function show(){ sets.forEach(s => s.hidden = +s.dataset.step !== step);
  document.getElementById('stepinfo').textContent = `${step}/3단계`;
  document.getElementById('back').hidden = step === 1;
  document.getElementById('next').textContent = step === 3 ? '요청 보내기' : '계속'; }
// Ripresa dal link nelle email: ?resume=<token> precompila i campi e salta al passo successivo.
(async () => { const tok = new URLSearchParams(location.search).get('resume'); if (!tok) return;
  try { const r = await fetch('/api/lead/' + encodeURIComponent(tok)); if (!r.ok) return; const d = await r.json();
    for (const [k, v] of Object.entries(d)) { const el = document.getElementById(k); if (el && v != null) el.value = v; }
    step = d.step || 2; show(); } catch(e){} })();
document.getElementById('back').onclick = () => { step--; show(); };
f.addEventListener('submit', e => { e.preventDefault(); const m = document.getElementById('msg'); m.textContent = '';
  if (step === 1 && !document.getElementById('email').checkValidity()) { m.textContent = '계속하려면 올바른 회사 이메일을 입력하세요.'; return; }
  if (step === 3 && !document.getElementById('consent').checked) { m.textContent = '회신을 위해 동의란에 체크해 주세요.'; return; }
  save(step === 3);
  if (step < 3) { step++; show(); } else { f.querySelectorAll('fieldset,.cta').forEach(x => x.hidden = true); m.textContent = '감사합니다. 영업일 1일 내에 회신드리겠습니다.'; } });
</script>

<script>(function(){var sj=new URLSearchParams(location.search).get('subject');var n=document.getElementById('notes');if(sj&&n&&!n.value)n.value='['+sj.slice(0,40)+'] ';})();</script>


---
Source: https://italygoyong.com/contact.html
