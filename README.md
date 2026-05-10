[index.html.html](https://github.com/user-attachments/files/27564812/index.html.html)
<!DOCTYPE html>
<html lang="ko">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>서촌 인문학 기행 2026</title>
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link href="https://fonts.googleapis.com/css2?family=Noto+Serif+KR:wght@400;600&family=Noto+Sans+KR:wght@300;400;500&display=swap" rel="stylesheet">
    <style>
        :root {
            --navy: #1A2D4A; --amber: #B85C00; --amberL:#FDF0E4; --bg: #FAFAF7;
            --text: #1A1917; --muted: #7A776E; --line: #E2DFD7; --card: #F4F2EC;
            --blue: #185FA5; --blueL:#E6F1FB; --green: #0F6E56; --greenL:#E1F5EE;
            --serif: 'Noto Serif KR', serif; --sans: 'Noto Sans KR', sans-serif; --r: 8px;
        }
        * { box-sizing: border-box; margin: 0; padding: 0; }
        body { font-family: var(--sans); background: var(--bg); color: var(--text); display: flex; flex-direction: column; min-height: 100vh; }
        
        /* 히어로 섹션 */
        .hero { background: var(--navy); padding: 40px 20px; text-align: center; color: #fff; }
        .hero-title { font-family: var(--serif); font-size: 24px; margin-bottom: 8px; }

        /* 사이드바 & 컨텐츠 레이아웃 */
        .main-container { display: flex; flex: 1; flex-direction: column; }
        @media (min-width: 769px) {
            .main-container { flex-direction: row; }
            .tab-nav { width: 240px; height: 100vh; position: sticky; top: 0; flex-direction: column !important; border-right: 1px solid var(--line); border-bottom: none !important; }
        }

        .tab-nav { display: flex; background: #fff; border-bottom: 1px solid var(--line); overflow-x: auto; position: sticky; top: 0; z-index: 10; }
        .tn { flex: 0 0 auto; padding: 15px 20px; border: none; background: none; cursor: pointer; color: var(--muted); text-align: left; font-weight: 500; transition: 0.2s; }
        .tn.on { color: var(--navy); border-left: 4px solid var(--amber); background: var(--amberL); }

        .tab-content { display: none; padding: 20px; max-width: 800px; margin: 0 auto; width: 100%; }
        .tab-content.on { display: block; }

        /* 미션 카드 & 업로드 스타일 */
        .mc { border: 1px solid var(--line); border-radius: var(--r); padding: 16px; margin-bottom: 15px; background: #fff; }
        .upload-wrapper { margin-top: 12px; }
        .upload-label { display: flex; align-items: center; justify-content: center; gap: 8px; border: 1.5px dashed var(--line); padding: 15px; cursor: pointer; border-radius: var(--r); font-size: 13px; color: var(--muted); }
        .preview-img { width: 100%; height: auto; border-radius: var(--r); margin-top: 10px; display: none; border: 1px solid var(--line); }
        .ans-input { width: 100%; border: 1px solid var(--line); border-radius: 6px; padding: 10px; margin-top: 8px; font-family: var(--sans); font-size: 14px; line-height: 1.6; }
        .example-text { font-size: 12px; color: var(--amber); background: var(--amberL); padding: 8px; border-radius: 4px; margin-bottom: 8px; border-left: 3px solid var(--amber); }
    </style>
</head>
<body>

<div class="hero">
    <div class="hero-title">서촌 인문학 기행 2026</div>
    <p style="font-size: 13px; opacity: 0.8;">사대부중 · 대곡중 · 시지고 연합 활동지</p>
</div>

<div class="main-container">
    <nav class="tab-nav">
        <button class="tn on" onclick="switchTab('guide', this)">🚩 여행 안내</button>
        <button class="tn" onclick="switchTab('mission', this)">📜 미션 여정</button>
        <button class="tn" onclick="switchTab('safety', this)">⚠️ 안전 지도</button>
    </nav>

    <div class="tab-content on" id="tab-guide">
        <h2>오늘의 일정</h2>
        <div class="mc">
            <p><strong>07:00</strong> 동대구역 출발 (KTX)</p>
            <p><strong>10:30</strong> 미션 1: 과학책방 갈다 탐방</p>
            <p><strong>12:30</strong> 미션 2: 통인시장 점심 식사</p>
            <p><strong>15:00</strong> 미션 4: 서촌 도보 탐방</p>
            <p><strong>17:00</strong> 최종 미션: 귀환 열차 내 선언문 작성</p>
        </div>
    </div>

    <div class="tab-content" id="tab-mission">
        <h2>미션 수행</h2>
        
        <div class="mc">
            <h3>미션 4. 서촌 탐방 기록</h3>
            <p class="fs12" style="margin-bottom:10px; color:var(--muted);">서촌에서 "오래된 것과 새로운 것이 함께 있는 장면"을 묘사해주세요.</p>
            
            <div class="example-text">
                <strong>💡 예시:</strong> 낡은 한옥 지붕 아래 현대적인 통유리 카페가 들어선 모습이 과거와 현재가 대화하는 것 같아 인상 깊었습니다.
            </div>

            <textarea class="ans-input" rows="3" placeholder="여기에 본인의 기록을 남겨주세요..."></textarea>
            
            <div class="upload-wrapper">
                <label class="upload-label" for="up-m4">📷 공존의 장면 사진 업로드</label>
                <input type="file" id="up-m4" class="upload-input" style="display:none" accept="image/*" onchange="previewImage(this)">
                <img src="" class="preview-img">
            </div>
        </div>

        <div class="mc" style="background:var(--greenL); border-color:var(--green);">
            <h3>📜 최종 미션: 인문학 기행 선언문</h3>
            <p class="fs12" style="margin-bottom:10px;">오늘의 경험을 한 문장으로 완성해 보세요.</p>
            
            <div class="example-text" style="background:#fff;">
                <strong>💡 예시:</strong> 나는 오늘 <u>서촌 골목길</u>을 통해 <u>기록의 중요성</u>을 깨달았다. 그래서 앞으로 <u>매일의 소중함을 글로 남기</u>겠다.
            </div>

            <textarea class="ans-input" rows="4" placeholder="나는 오늘 ___을(를) 통해 ___을(를) 깨달았다. 그래서 앞으로 ___하겠다."></textarea>
        </div>
    </div>

    <div class="tab-content" id="tab-safety">
        <h2>안전 수칙 및 비상 연락망</h2>
        <div class="mc">
            <ul style="padding-left: 20px; line-height: 2;">
                <li>승차권 분실 주의 및 2인 1조 이동 유지</li>
                <li>전시물 무단 접촉 금지 및 촬영 규정 준수</li>
                <li><strong>집결지:</strong> 경복궁역 3번 출구</li>
                <li><strong>비상 연락:</strong> 119 또는 인솔 선생님 핸드폰</li>
            </ul>
        </div>
    </div>
</div>

<script>
    // 탭 전환 함수
    function switchTab(tabId, btn) {
        document.querySelectorAll('.tab-content').forEach(c => c.classList.remove('on'));
        document.querySelectorAll('.tn').forEach(b => b.classList.remove('on'));
        document.getElementById('tab-' + tabId).classList.add('on');
        btn.classList.add('on');
        window.scrollTo(0,0);
    }

    // 이미지 미리보기 함수
    function previewImage(input) {
        const preview = input.nextElementSibling;
        const file = input.files[0];
        if (file) {
            const reader = new FileReader();
            reader.onload = e => {
                preview.src = e.target.result;
                preview.style.display = 'block';
                input.previousElementSibling.innerHTML = '✅ 사진 업로드 완료';
            }
            reader.readAsDataURL(file);
        }
    }
</script>

</body>
</html>
