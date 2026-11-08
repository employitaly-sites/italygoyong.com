# 이탈리아 인건비 계산기

> 이탈리아 직원 1명의 총비용: 세전 연봉, 사용자 사회보험료, INAIL, 퇴직금 적립을 두 가지 단체협약 예시로 계산하고, 주·시 지방세가 실수령액에 미치는 영향을 설명합니다.


<section> <span class="eyebrow">비용 계산기</span> <h1 id="what-an-employee-in-italy-really-costs">이탈리아 직원의 실제 비용</h1> <p class="lede">귀사는 직원의 실제 인건비와 저희 월 요금을 부담합니다. 한국의 4대보험·퇴직금 감각으로 계산하면 적게 잡히기 쉽습니다. 두 가지 단체협약 예시로 인건비 구성을 보여드립니다.</p> </section> <section> <div class="grid"> <form class="panel" id="calc" style="display:grid;gap:16px"> <label for="ral">세전 연봉 RAL (EUR)<input id="ral" type="number" min="15000" step="1000" value="50000"></label> <label for="ccnl">단체협약 (CCNL)<select id="ccnl"><option value="commercio">상업·서비스 (CCNL Terziario, Distribuzione e Servizi)</option><option value="metalmeccanico">엔지니어링·제조 (CCNL Metalmeccanico Industria)</option></select></label> <label style="display:flex;gap:10px;align-items:center;font-weight:400"><input id="prorata" type="checkbox" checked style="width:auto">13월·14월 급여를 매월 급여에 비례 분할 지급</label> <label style="display:flex;gap:10px;align-items:center;font-weight:400"><input id="tfrfund" type="checkbox" checked style="width:auto">TFR을 매월 직원이 선택한 기금에 납입</label> <label for="fx">EUR당 USD 환율<input id="fx" type="number" step="0.01" value="1.08"></label> <p id="ccnlnote" style="margin:0;color:var(--muted);font-size:14px"></p> </form> <div class="panel" style="min-width:0"> <div class="tbl"><table id="out"> <thead><tr><th>항목</th><th class="num">월 (평균)</th><th class="num">연간</th></tr></thead> <tbody></tbody> </table></div> <p id="inst" style="font-size:14px;color:var(--muted);margin-bottom:0"></p> </div> </div> <p style="font-size:14px;color:var(--muted)">예시 수치이며 요율은 2026-10-26 기준입니다. 보험료와 보험 요율은 참고치 <span class="tag">추정</span>이며 정확한 업종, 회사 규모, 직무 위험 등급에 따라 달라집니다. 견적에서 확정해 드립니다. 원화 청구액은 발행일 EUR 기준환율로 환산합니다.</p> </section> <section> <h2 id="your-monthly-invoices-over-a-year">1년간 월별 청구서</h2> <p class="prose" style="margin:0">연간 비용은 어느 쪽이든 같습니다. 옵션은 지급 시점만 바꿉니다. 두 옵션을 모두 켜면 매월 같은 금액이 나가고 나중에 쌓이는 부담이 없습니다. 견적은 이 방식으로 작성합니다.</p> <div class="tbl"><table id="sched"><thead><tr><th>월</th><th class="num">급여</th><th class="num">INPS + INAIL</th><th class="num">TFR</th><th class="num">요금</th><th class="num">청구액</th></tr></thead><tbody></tbody></table></div> <p id="schednote" style="font-size:14px;color:var(--muted);margin:0"></p>  </section> <section class="prose"> <h2 id="what-the-employment-cost-is-made-of">인건비의 구성</h2> <div class="fact"><b>RAL</b><span><strong>세전 연봉.</strong> 오퍼레터의 금액입니다. CCNL에 따라 13회 또는 14회로 지급하며, 추가분은 13월 급여(12월)와 상업·서비스 협약의 14월 급여(7월)입니다.</span></div> <div class="fact"><b>INPS</b><span><strong>사용자 사회보험료.</strong> 연금, 실업, 질병, 출산 기금으로 세전의 약 29–32%입니다. 직원은 세전 급여에서 약 9%를 따로 내며, 이는 귀사의 추가 비용이 아닙니다.</span></div> <div class="fact"><b>INAIL</b><span><strong>산재보험.</strong> 의무입니다. 사무직은 낮고(1% 훨씬 미만), 기술·생산직은 높습니다.</span></div> <div class="fact"><b>TFR</b><span><strong>퇴직금 적립.</strong> 세전의 6.91%를 매년 적립해 사유와 관계없이 퇴사 시 지급합니다(민법 제2120조).</span></div> <div class="fact"><b>Fee</b><span><strong>저희 EOR 요금.</strong> 직원 1인당 월 €250.</span></div> </section> <section class="prose"> <h2 id="billed-on-actuals-month-by-month">매월 실제 금액으로 청구</h2> <p>위 표는 추정치입니다. 매월 실제 급여를 처리하고 실제 비용을 청구합니다. 연장근로, 보너스, 무급휴가, INPS가 일부 부담하는 병가, 급여 변경, CCNL 인상분이 모두 그 달 금액에 반영됩니다. 매 청구서에 급여 요약이 첨부되어 모든 항목을 확인할 수 있습니다.</p> <p>결제 조건: 시작 시 1개월분 예상 비용을 환급 가능한 보증금으로, 첫 달 1개월분을 선불로 받습니다. 이후 매월 예상액으로 선불 결제하고 다음 청구서에서 실제 급여로 정산합니다.</p> </section> <section class="prose"> <h2 id="two-collective-agreements-compared">두 단체협약 비교</h2> <p>같은 RAL €50,000이라도 금속기계 협약의 엔지니어 계약은 상업·서비스 협약의 사무직 계약보다 사용자 비용이 연 약 €1,500–2,000 더 듭니다. 사회보험 요율이 약 2–3%p 높고 기술직 산재보험료도 높기 때문입니다. 상업 협약은 14회로 지급해 매월 명세서 금액은 작지만 연간 RAL은 같습니다.</p> <p>어떤 협약을 적용할지는 자유 선택이 아니라 직무와 업종에 따라 정해집니다. 계약서 초안에서 선택하고 이유를 설명드립니다.</p> </section> <section class="prose"> <h2 id="why-the-city-changes-net-pay-not-your-cost">도시는 실수령액을 바꾸지만 귀사 비용은 바꾸지 않습니다</h2> <p>국세인 IRPEF 외에 모든 직원은 <strong>주</strong> 부가세(주와 소득 구간에 따라 과세소득의 1.23%에서 약 3.33%)와 <strong>시</strong> 부가세(보통 0–0.8%, 로마 0.9%, 나폴리 1%, 토리노 최고 1.2%, 저소득 면제 도시 많음)를 냅니다. 둘 다 직원의 세전 급여에서 원천징수합니다.</p> <p>귀사가 내는 금액은 바뀌지 않고 직원의 실수령액만 바뀝니다. RAL €50,000 기준으로 가장 유리한 주·시 조합과 가장 불리한 조합의 차이는 연 €1,000–1,500 정도입니다. 다른 도시 후보자들의 오퍼를 비교할 때 알아두세요.</p>  </section> <div class="cta"><a class="btn" href="contact.html">정확한 견적 받기</a><a class="btn ghost" href="net-pay-calculator.html">직원 실수령액 보기</a></div> <script>(function(){const P = {"_note":"Parametri del calcolatore con fonte e stato. 'indicative' = da sostituire con data/params/2026.yaml verificato.","updated":"2026-10-26","ccnl":{"commercio":{"label":"Commerce and services (CCNL Terziario, Distribuzione e Servizi)","installments":14,"employer_social_rate":0.29,"inail_rate":0.004,"status":"indicative","note":"사무직, IT 서비스, 컨설팅, 영업에 일반적. 13월·14월 급여."},"metalmeccanico":{"label":"Engineering and manufacturing (CCNL Metalmeccanico Industria)","installments":13,"employer_social_rate":0.315,"inail_rate":0.012,"status":"indicative","note":"엔지니어링, 생산, 기술직에 일반적. 13월 급여."}},"tfr_rate":{"value":0.0691,"status":"verified","source":"Civil Code art. 2120: gross pay / 13.5, less 0.5% to the INPS fund"},"employee_social_rate":{"value":0.0919,"status":"indicative","source":"INPS employee share, private sector"},"regional_surcharge":{"min":0.0123,"max":0.0333,"status":"indicative","source":"MEF, addizionale regionale IRPEF"},"municipal_surcharge":{"min":0,"max":0.009,"status":"indicative","source":"MEF, addizionale comunale IRPEF (0.8% general cap; Rome 0.9%)"},"eor_fee_eur":{"value":250,"status":"list price"},"usd_per_eur":{"value":1.08,"status":"indicative","source":"Replace with ECB daily reference rate at build time"},"net":{"status":"secondary","source":"data/params/2026.yaml (irpef, inps, addizionali); TUIR art. 11 and 13; L. 207/2024; L. 199/2025","employee_inps":0.0919,"extra_1pct_above":56224,"irpef":[[28000,0.23],[50000,0.33],[null,0.43]],"cities":{"Milan":{"region":"Lombardy","regional":[[null,0.0123]],"municipal":0.008,"exempt":23000},"Rome":{"region":"Lazio","regional":[[28000,0.0173],[null,0.0333]],"municipal":0.009,"exempt":14000},"Turin":{"region":"Piedmont","regional":[[null,0.0162]],"municipal":0.008,"municipal_note":"0.8% to 1.2% by band; 0.8% used","exempt":11790},"Bologna":{"region":"Emilia-Romagna","regional":[[null,0.0133]],"municipal":0.008,"exempt":15000},"Naples":{"region":"Campania","regional":[[null,0.0173]],"municipal":0.01,"exempt":12000}}}};

const eur = n => '€' + Math.round(n).toLocaleString('en-US');
const usd = n => '$' + Math.round(n).toLocaleString('en-US');
function calc(){
  const ral = +document.getElementById('ral').value || 0;
  const fx = +document.getElementById('fx').value || 0;
  const c = P.ccnl[document.getElementById('ccnl').value];
  const items = [
    ['세전 연봉 (RAL)', ral],
    ['사용자 사회보험료 (INPS)', ral * c.employer_social_rate],
    ['산재보험 (INAIL)', ral * c.inail_rate],
    ['퇴직금 적립 (TFR)', ral * P.tfr_rate.value],
    ['이탈리아 고용 EOR 요금', P.eor_fee_eur.value * 12],
  ];
  const tot = items.reduce((s, x) => s + x[1], 0);
  document.querySelector('#out tbody').innerHTML = items.map(([k, v]) => `<tr><td>${k}</td><td class="num">${eur(v/12)}</td><td class="num">${eur(v)}</td></tr>`).join('')
    + `<tr><td><b>총비용</b></td><td class="num"><b>${eur(tot/12)}</b></td><td class="num"><b>${eur(tot)}</b></td></tr>`
    + `<tr><td>USD 환산 총액</td><td class="num">${usd(tot/12*fx)}</td><td class="num">${usd(tot*fx)}</td></tr>`;
  document.getElementById('inst').textContent = `급여는 세전 ${eur(ral / c.installments)}씩 ${c.installments}회 지급됩니다. 총비용은 RAL보다 ${(tot / ral * 100 - 100).toFixed(0)}% 높습니다.`;
  document.getElementById('ccnlnote').textContent = c.note;
  const pr = document.getElementById('prorata').checked, tf = document.getElementById('tfrfund').checked;
  const inst = ral / c.installments, extra = c.installments - 12;
  const months = ['1월','2월','3월','4월','5월','6월','7월','8월','9월','10월','11월','12월'];
  const rate = c.employer_social_rate + c.inail_rate, fee = P.eor_fee_eur.value;
  let rows = '', sum = 0;
  months.forEach((m, i) => {
    let sal = pr ? ral / 12 : inst + (i === 11 ? inst : 0) + (extra === 2 && i === 6 ? inst : 0);
    const tfr = tf ? ral * P.tfr_rate.value / 12 : 0;
    const inv = sal * (1 + rate) + tfr + fee; sum += inv;
    rows += `<tr><td>${m}</td><td class="num">${eur(sal)}</td><td class="num">${eur(sal*rate)}</td><td class="num">${eur(tfr)}</td><td class="num">${eur(fee)}</td><td class="num"><b>${eur(inv)}</b></td></tr>`;
  });
  rows += `<tr><td><b>연간</b></td><td></td><td></td><td></td><td></td><td class="num"><b>${eur(sum)}</b></td></tr>`;
  document.querySelector('#sched tbody').innerHTML = rows;
  document.getElementById('schednote').textContent = tf ? 'TFR을 매월 납입하므로 퇴직금 부채가 쌓이지 않습니다.' : `연 ${eur(ral * P.tfr_rate.value)}의 TFR이 적립되어 퇴사 시 지급되며, 보증금으로 담보됩니다.`;
}
document.getElementById('calc').addEventListener('input', calc);
document.getElementById('calc').addEventListener('submit', e => e.preventDefault());
calc();
})();</script>


---
Source: https://italygoyong.com/calculator.html
