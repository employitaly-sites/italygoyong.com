# 이탈리아 실수령액 계산기

> 2026년 이탈리아 세전→실수령: 직원 사회보험료, 근로소득 세액공제를 반영한 소득세(IRPEF), 주·시 부가세. 밀라노, 로마, 토리노, 볼로냐, 나폴리.


<section> <span class="eyebrow">실수령액 계산기</span> <h1 id="what-your-employee-takes-home-in-italy">이탈리아 직원이 실제로 받는 금액</h1> <p class="lede">세전 연봉과 도시를 입력하세요. 2026년 규칙(직원 사회보험료, 근로소득 세액공제를 반영한 소득세, 지방 부가세)을 적용한 추정치입니다. 한국의 연봉 실수령액 표처럼 후보자와 대화할 때 쓰세요.</p> </section> <section> <div class="grid"> <form class="panel" id="nf" style="display:grid;gap:16px"> <label for="g">세전 연봉 RAL (EUR)<input id="g" type="number" min="10000" step="1000" value="50000"></label> <label for="city">도시<select id="city"><option value="Milan">밀라노</option><option value="Rome">로마</option><option value="Turin">토리노</option><option value="Bologna">볼로냐</option><option value="Naples">나폴리</option></select></label> <label for="inst">지급 횟수<select id="inst"><option value="13">13회</option><option value="14">14회</option><option value="12">12회 (13월·14월 비례 분할)</option></select></label> </form> <div class="panel" style="min-width:0"><div class="tbl"><table id="nt"><thead><tr><th>항목</th><th class="num">연간</th></tr></thead><tbody></tbody></table></div> <p id="nm" style="margin-bottom:0;font-weight:600"></p></div> </div>  </section> <section class="prose"> <h2 id="how-the-calculation-works">계산 방식</h2> <ol> <li>직원은 세전 급여의 9.19%를 사회보험료로 내고, 연 €56,224 초과분에는 1%를 더 냅니다.</li> <li>나머지에 소득세(IRPEF)가 붙습니다: €28,000까지 23%, €28,000–€50,000 33%, 초과분 43%.</li> <li>근로소득 세액공제가 세금을 줄입니다. 저연봉에서 가장 크고 €50,000에서 0이 됩니다. €20,000–€40,000 구간에는 최대 €1,000의 추가 공제가 있습니다.</li> <li>주·시 부가세가 더해지며, 소득이 시 면세 기준보다 낮으면 시 부가세는 없습니다.</li> </ol> <p>이 중 어느 것도 사용자 부담액을 바꾸지 않습니다. <a href="calculator.html">사용자 비용 계산기</a>를 보세요.</p> </section> <script>(function(){const N = {"status":"secondary","source":"data/params/2026.yaml (irpef, inps, addizionali); TUIR art. 11 and 13; L. 207/2024; L. 199/2025","employee_inps":0.0919,"extra_1pct_above":56224,"irpef":[[28000,0.23],[50000,0.33],[null,0.43]],"cities":{"Milan":{"region":"롬바르디아","regional":[[null,0.0123]],"municipal":0.008,"exempt":23000},"Rome":{"region":"라치오","regional":[[28000,0.0173],[null,0.0333]],"municipal":0.009,"exempt":14000},"Turin":{"region":"피에몬테","regional":[[null,0.0162]],"municipal":0.008,"municipal_note":"0.8% to 1.2% by band; 0.8% used","exempt":11790},"Bologna":{"region":"에밀리아로마냐","regional":[[null,0.0133]],"municipal":0.008,"exempt":15000},"Naples":{"region":"캄파니아","regional":[[null,0.0173]],"municipal":0.01,"exempt":12000}}};

const eur = n => (n < 0 ? '−€' : '€') + Math.round(Math.abs(n)).toLocaleString('en-US');
function bands(x, b){ let t = 0, lo = 0; for (const [hi, r] of b){ const top = hi ?? Infinity; if (x > lo) t += (Math.min(x, top) - lo) * r; lo = top; } return t; }
function credit(r){ if (r <= 15000) return 1955; if (r <= 28000) return 1910 + 1190 * (28000 - r) / 13000; if (r <= 50000) return 1910 * (50000 - r) / 22000 + (r > 25000 && r <= 35000 ? 65 : 0); return 0; }
function extra(r){ if (r > 20000 && r <= 32000) return 1000; if (r > 32000 && r < 40000) return 1000 * (40000 - r) / 8000; return 0; }
function calc(){
  const g = +document.getElementById('g').value || 0, c = N.cities[document.getElementById('city').value], n = +document.getElementById('inst').value;
  const inps = g * N.employee_inps + Math.max(0, g - N.extra_1pct_above) * 0.01;
  const tx = g - inps;
  const irpef = Math.max(0, bands(tx, N.irpef) - credit(tx) - extra(tx));
  const reg = bands(tx, c.regional), mun = tx > c.exempt ? tx * c.municipal : 0;
  const net = g - inps - irpef - reg - mun;
  const rows = [['세전 연봉', g], ['직원 사회보험료', -inps], ['세액공제 후 소득세 (IRPEF)', -irpef], [`주 부가세 (${c.region})`, -reg], ['시 부가세', -mun]];
  document.querySelector('#nt tbody').innerHTML = rows.map(([k, v]) => `<tr><td>${k}</td><td class="num">${eur(v)}</td></tr>`).join('') + `<tr><td><b>실수령액</b></td><td class="num"><b>${eur(net)}</b></td></tr>`;
  document.getElementById('nm').textContent = `월 명세서 ${n}회 각각 약 ${eur(net / n)} 실수령 (세전의 ${(net / g * 100).toFixed(0)}%).`;
}
document.getElementById('nf').addEventListener('input', calc); document.getElementById('nf').addEventListener('submit', e => e.preventDefault()); calc();
})();</script>


---
Source: https://italygoyong.com/net-pay-calculator.html
