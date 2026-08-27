<html lang="th" class="h-full">
 <head><script>window["__codeletBootstrap__"]=JSON.parse('{"A":"A","B":"20260827-05-ff67167","C":{"Abril Fatface":"YACgEZbkUVE,0","Alfa Slab One":"YACgEYS9sJU,0","Anton":"YACgEcYqQ-A,0","Archivo":"YAHO2-t-jNE,0","Arial":"YAGyDvJ_4Ts,0","Bebas Neue":"YACgESME5ew,0","Bricolage Grotesque":"YAFyMcdwzpc,0","Canva Sans":"YAFLd8sKbwc,2","Caveat":"YALBs2ploWQ,0","Comic Sans MS":"YAHO2VMiyZo,0","Cormorant Garamond":"YAFdJhX-538,0","Courier New":"YAGzXiGs0_8,0","DM Sans":"YAD1aU3sLnI,0","DM Serif Display":"YAD1aYG82rc,0","Forum":"YACgEcnnqB4,0","Fraunces":"YAEul-FRQw4,0","Georgia":"YAGzXkO0pEM,0","Helvetica Neue":"YAFcf6CtJfI,0","Impact":"YAFcfnjI7Vk,0","Inter":"YAFdJvSyp_k,3","Iowan Old Style":"YAGNIFa8j9o,0","Jacques Francois":"YAHO2a5g66Q,0","JetBrains Mono":"YAFdJksXcAk,0","Libre Baskerville":"YACgEUFdPdA,0","Manrope":"YAHO2b2feC4,0","Merriweather":"YACgEXvHxxs,0","Montserrat":"YADLjI9qxTA,0","Nunito":"YACgEX8C5Gg,0","Oleo Script":"YACgEQQ14jI,0","Phantom Sans":"YAHO2E8Pb88,0","Playfair Display":"YACgEYmuCJE,0","Poppins":"YAFdJjbTu24,1","Press Start 2P":"YAFyGr-8pmQ,0","Quicksand":"YADWjpfPmdk,0","Raleway":"YACgEVg3xZg,0","Segoe UI":"YAHNdRD1Klw,0","Source Sans 3":"YAG4lO1Mj10,0","Spectral":"YAHO2rVUHIM,0","Times New Roman":"YAGzXW3gftg,0","Times":"YAGzXW3gftg,0","Ubuntu":"YACgERDU--Q,0","Work Sans":"YAGXhLOKv44,0","Yellowtail":"YACgEYG4kG4,0","ui-monospace":"YADlN8CFZ8Q,0","ui-sans-serif":"YACkoN-xg4g,0"}}');</script><script src="/_sdk/50d846425a1e5082.telemetry_sdk.js" integrity="sha512-Otbex+ztlVbcEGql0rXGd/3E3ee/hqAntg6DeuUEMG6pIPbXGOSvZbFZVzknAXi1tH/itQ+ijEhOTr2aWj6CXg=="></script>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>ระบบประกาศคะแนนสอบ</title>
  <script src="/_sdk/176239d78dc337f0.element_sdk.js" integrity="sha512-QC7TZpezTofrkWmJhkdnKO24kgkRY/EHV5cad+uwo8N4ozX9ri23FZJi6dkIeKf6YH+zcqWLm9sdXZ0HWhu7eg=="></script>
  <script src="https://cdn.tailwindcss.com"></script>
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstapi.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Mitr:wght@300;400;500;600;700&amp;display=swap" rel="stylesheet">
  <style>
    body {
      box-sizing: border-box;
      font-family: 'Mitr', sans-serif;
    }
  </style>
  <script src="https://cdn.tailwindcss.com/3.4.17" type="text/javascript"></script>
  <script src="/_sdk/b3bf9e8ac58e6ad6.data_sdk.js" type="text/javascript" integrity="sha512-otc1u9NYq9Ms5Jt//7vmhrrqR5CLPr8Jdgs6741gqniClfLMcfmC+jK/cKuQdhLv6G0esJ/FzaMS9tv0T/vj/Q=="></script>
  <script src="https://cdn.jsdelivr.net/npm/lucide@0.263.0/dist/umd/lucide.min.js" type="text/javascript"></script>
 </head>
 <body class="h-full">
  <div id="app" class="h-full w-full"></div>
  <script>
    const PASSWORD = "305MEP69";
    const MAX_SCORE = 20;
    const chapterTitles = [
      "จำนวนนับไม่เกิน 100,000",
      "การบวกและการลบจำนวนนับไม่เกิน 100,000",
      "เวลา",
      "รูปเรขาคณิต",
      "แผนภูมิรูปภาพและตารางทางเดียว",
      "เศษส่วน",
      "การคูณ"
    ];
    
    const defaultConfig = {
      school_name: "โรงเรียนประตูชัย",
      class_name: "ชั้นประถมศึกษาปีที่ 3/5",
      subject_name: "สาย MEP (Mini English Program)",
      teacher_name: "นางวิรัลพัชษ์ สว่างเดือน",
      background_color: "#fef3e2",
      card_color: "#fffef5",
      primary_color: "#f97316",
      text_color: "#7c2d12",
      accent_color: "#9333ea",
      font_family: "Mitr",
      font_size: 16
    };

    // ข้อมูลนักเรียนทั้งหมด
    const studentsData = {
      "22321": { name: "เด็กชายภัทรพล แกนยางหวาย", chapter1: 16.5, chapter2: 13, chapter3: 19, chapter4: "-", chapter5: "-" },
      "22330": { name: "เด็กชายเอกศิษฎ์ ทองสกุล", chapter1: 14, chapter2: 13, chapter3: 10, chapter4: "-", chapter5: "-" },
      "22335": { name: "เด็กชายภิญญาพัชญ์ เปรมสุข", chapter1: 14, chapter2: 6, chapter3: 8, chapter4: "-", chapter5: "-" },
      "22337": { name: "เด็กชายเมธาสิทธิ์ คงนุมัติ", chapter1: 5, chapter2: 7, chapter3: 4, chapter4: "-", chapter5: "-" },
      "22345": { name: "เด็กชายณัฎฐ์ตฤณ สุขประเสริฐ", chapter1: 18, chapter2: 16, chapter3: 15, chapter4: "-", chapter5: "-" },
      "22364": { name: "เด็กชายณภัทร แช่มวงศ์", chapter1: 12.5, chapter2: 7, chapter3: 8, chapter4: "-", chapter5: "-" },
      "22386": { name: "เด็กชายมีคุณ รัตนานนท์", chapter1: 13, chapter2: 11.5, chapter3: 13, chapter4: "-", chapter5: "-" },
      "22795": { name: "เด็กชายวรปรัชญ์ กิจเปรมถาวร", chapter1: 12.5, chapter2: 7.5, chapter3: 14, chapter4: "-", chapter5: "-" },
      "23364": { name: "เด็กชายเป็นไทย แก้วแดง", chapter1: 17, chapter2: 14, chapter3: 14, chapter4: "-", chapter5: "-" },
      "23365": { name: "เด็กชายรัตนพล เอมนฤมล", chapter1: 15, chapter2: 13, chapter3: 9, chapter4: "-", chapter5: "-" },
      "23366": { name: "เด็กชายสุกฤษฎิ์ ขอเสริมกลาง", chapter1: 19.5, chapter2: 17, chapter3: 13, chapter4: "-", chapter5: "-" },
      "23367": { name: "เด็กชายธนวัฒน์ พรไตรรัตน์", chapter1: 12.5, chapter2: 7, chapter3: 6, chapter4: "-", chapter5: "-" },
      "23368": { name: "เด็กชายณัฐพนธ์ กันชะนะ", chapter1: 13.5, chapter2: 11, chapter3: 10, chapter4: "-", chapter5: "-" },
      "23369": { name: "เด็กชายกมลภพ ขยายฤทธิ์", chapter1: 4, chapter2: 4, chapter3: 6, chapter4: "-", chapter5: "-" },
      "22324": { name: "เด็กหญิงณัฐชนก พงษ์พิทักษ์วิเศษ", chapter1: 12.5, chapter2: 9, chapter3: 9, chapter4: "-", chapter5: "-" },
      "22327": { name: "เด็กหญิงปวริศา กงฉิน", chapter1: 12.5, chapter2: 14, chapter3: 4, chapter4: "-", chapter5: "-" },
      "22351": { name: "เด็กหญิงรดา อินเที่ยง", chapter1: 17.5, chapter2: 12, chapter3: 14, chapter4: "-", chapter5: "-" },
      "22366": { name: "เด็กหญิงออมสิน พบสุข", chapter1: 7.5, chapter2: 6, chapter3: 4, chapter4: "-", chapter5: "-" },
      "22370": { name: "เด็กหญิงปทิตตา ชัยพฤกษ์", chapter1: 11, chapter2: 11, chapter3: 11, chapter4: "-", chapter5: "-" },
      "22798": { name: "เด็กหญิงรวินท์นิภา โตแทน", chapter1: 18.5, chapter2: 19, chapter3: 16, chapter4: "-", chapter5: "-" },
      "23088": { name: "เด็กหญิงปวริศา กายจริต", chapter1: 2.5, chapter2: "ขาดสอบ", chapter3: "ขาดสอบ", chapter4: "-", chapter5: "-" },
      "23370": { name: "เด็กหญิงธนันรดา ผาสุขถิน", chapter1: 14.5, chapter2: 12, chapter3: 14, chapter4: "-", chapter5: "-" },
      "23371": { name: "เด็กหญิงปุญณดา คงสมจิตร์", chapter1: 16, chapter2: 17, chapter3: 18, chapter4: "-", chapter5: "-" },
      "23373": { name: "เด็กหญิงทักษิยนันท์ สุจริตพงษ์", chapter1: 10, chapter2: 1, chapter3: 9, chapter4: "-", chapter5: "-" },
      "23374": { name: "เด็กหญิงวนัฏษญา แสนกือ", chapter1: 1.5, chapter2: 1, chapter3: 5, chapter4: "-", chapter5: "-" },
      "23375": { name: "เด็กหญิงสุพิชญา วังหอม", chapter1: 15.5, chapter2: 14.5, chapter3: 10, chapter4: "-", chapter5: "-" },
      "23376": { name: "เด็กหญิงปุญฐิตา เฉลิมโภชน์", chapter1: 5, chapter2: 10, chapter3: 4, chapter4: "-", chapter5: "-" },
      "23377": { name: "เด็กหญิงณภัทร พุ่มพวง", chapter1: 2, chapter2: 12, chapter3: 6, chapter4: "-", chapter5: "-" },
      "24266": { name: "เด็กหญิงวรชาดา พูลเจริญ", chapter1: 12.5, chapter2: 16, chapter3: 11, chapter4: "-", chapter5: "-" }
    };

    let currentStudentId = null;

    async function initApp() {
      if (window.elementSdk) {
        window.elementSdk.init({
          defaultConfig,
          onConfigChange: async (config) => {
            applyConfig(config);
            if (currentStudentId) {
              renderScoresPage();
            } else {
              renderLoginPage();
            }
          },
          mapToCapabilities: (config) => ({
            recolorables: [
              {
                get: () => config.background_color || defaultConfig.background_color,
                set: (value) => {
                  config.background_color = value;
                  window.elementSdk.setConfig({ background_color: value });
                }
              },
              {
                get: () => config.card_color || defaultConfig.card_color,
                set: (value) => {
                  config.card_color = value;
                  window.elementSdk.setConfig({ card_color: value });
                }
              },
              {
                get: () => config.text_color || defaultConfig.text_color,
                set: (value) => {
                  config.text_color = value;
                  window.elementSdk.setConfig({ text_color: value });
                }
              },
              {
                get: () => config.primary_color || defaultConfig.primary_color,
                set: (value) => {
                  config.primary_color = value;
                  window.elementSdk.setConfig({ primary_color: value });
                }
              },
              {
                get: () => config.accent_color || defaultConfig.accent_color,
                set: (value) => {
                  config.accent_color = value;
                  window.elementSdk.setConfig({ accent_color: value });
                }
              }
            ],
            borderables: [],
            fontEditable: {
              get: () => config.font_family || defaultConfig.font_family,
              set: (value) => {
                config.font_family = value;
                window.elementSdk.setConfig({ font_family: value });
              }
            },
            fontSizeable: {
              get: () => config.font_size || defaultConfig.font_size,
              set: (value) => {
                config.font_size = value;
                window.elementSdk.setConfig({ font_size: value });
              }
            }
          }),
          mapToEditPanelValues: (config) => new Map([
            ["school_name", config.school_name || defaultConfig.school_name],
            ["class_name", config.class_name || defaultConfig.class_name],
            ["subject_name", config.subject_name || defaultConfig.subject_name],
            ["teacher_name", config.teacher_name || defaultConfig.teacher_name]
          ])
        });
      }

      renderLoginPage();
    }

    function applyConfig(config) {
      const app = document.getElementById('app');
      const customFont = config.font_family || defaultConfig.font_family;
      const baseSize = config.font_size || defaultConfig.font_size;
      const bgColor = config.background_color || defaultConfig.background_color;
      
      app.style.background = `linear-gradient(135deg, ${bgColor} 0%, #f5e6f0 50%, #fce7f3 100%)`;
      app.style.fontFamily = `${customFont}, sans-serif`;
      app.style.fontSize = `${baseSize}px`;
      
      document.documentElement.style.setProperty('--card-color', config.card_color || defaultConfig.card_color);
      document.documentElement.style.setProperty('--text-color', config.text_color || defaultConfig.text_color);
      document.documentElement.style.setProperty('--primary-color', config.primary_color || defaultConfig.primary_color);
      document.documentElement.style.setProperty('--accent-color', config.accent_color || defaultConfig.accent_color);
    }

    function renderLoginPage() {
      const config = window.elementSdk?.config || defaultConfig;
      const app = document.getElementById('app');
      const customFont = config.font_family || defaultConfig.font_family;
      const baseSize = config.font_size || defaultConfig.font_size;
      const cardColor = config.card_color || defaultConfig.card_color;
      const textColor = config.text_color || defaultConfig.text_color;
      const primaryColor = config.primary_color || defaultConfig.primary_color;
      const schoolName = config.school_name || defaultConfig.school_name;
      const className = config.class_name || defaultConfig.class_name;
      const subjectName = config.subject_name || defaultConfig.subject_name;
      const teacherName = config.teacher_name || defaultConfig.teacher_name;

      app.innerHTML = `
        <div class="h-full w-full flex items-center justify-center p-6" style="background: linear-gradient(135deg, #fef3e2 0%, #fbe8d3 50%, #fef3e2 100%); overflow-y: auto; position: relative;">
          <div style="position: absolute; top: 20px; left: 30px; font-size: 48px; opacity: 0.7; animation: float 3s ease-in-out infinite;">🎀</div>
          <div style="position: absolute; top: 100px; right: 40px; font-size: 40px; opacity: 0.6; animation: float 4s ease-in-out infinite; animation-delay: 1s;">🍭</div>
          <div style="position: absolute; bottom: 120px; left: 50px; font-size: 44px; opacity: 0.65; animation: float 3.5s ease-in-out infinite; animation-delay: 0.5s;">🍦</div>
          <div style="position: absolute; bottom: 200px; right: 60px; font-size: 42px; opacity: 0.6; animation: float 4.5s ease-in-out infinite; animation-delay: 1.5s;">🎀</div>
          <style>
            @keyframes float {
              0%, 100% { transform: translateY(0px); }
              50% { transform: translateY(-20px); }
            }
          </style>
          <div class="w-full max-w-md" style="background: ${cardColor}; border-radius: 24px; box-shadow: 0 12px 40px rgba(124, 58, 237, 0.2); padding: 48px; border: 3px solid rgba(124, 58, 237, 0.15); position: relative;">
            <div style="position: absolute; top: -15px; left: 20px; font-size: 32px;">🎀</div>
            <div style="position: absolute; top: -15px; right: 20px; font-size: 32px;">🍭</div>
            <div style="text-align: center; margin-bottom: 32px;">
              <div style="font-size: ${baseSize * 1.76}px; font-weight: 700; background: linear-gradient(135deg, #f97316 0%, #9333ea 50%, #a855f7 100%); -webkit-background-clip: text; -webkit-text-fill-color: transparent; background-clip: text; margin-bottom: 16px; font-family: ${customFont}, sans-serif; line-height: 1.3;">
                🌟 ระบบประกาศคะแนนวิชาคณิตศาสตร์สาย MEP
              </div>
              <div style="font-size: ${baseSize * 1.1}px; font-weight: 600; color: ${textColor}; margin-bottom: 8px; font-family: ${customFont}, sans-serif;">
                ${schoolName}
              </div>
              <div style="font-size: ${baseSize * 0.95}px; color: ${textColor}; opacity: 0.8; margin-bottom: 6px; font-family: ${customFont}, sans-serif;">
                ${className}
              </div>
              <div style="font-size: ${baseSize * 0.9}px; color: ${textColor}; opacity: 0.7; margin-bottom: 8px; font-family: ${customFont}, sans-serif;">
                ${subjectName}
              </div>
              <div style="font-size: ${baseSize * 0.95}px; font-weight: 700; color: ${textColor}; opacity: 0.85; font-family: ${customFont}, sans-serif;">
                ครูผู้สอน ${teacherName}
              </div>
            </div>

            <div style="margin-bottom: 24px; padding: 20px; background: linear-gradient(135deg, #fce7f3 0%, #f3e8ff 100%); border-radius: 16px; border: 2px solid #a855f7;">
              <div style="font-size: ${baseSize * 1.05}px; font-weight: 700; color: #6b21a8; margin-bottom: 12px; font-family: ${customFont}, sans-serif; display: flex; align-items: center; gap: 8px;">
                <span style="font-size: ${baseSize * 1.3}px;">ℹ️</span>
                คำแนะนำการเข้าใช้งาน
              </div>
              <div style="font-size: ${baseSize * 0.85}px; color: #7c3aed; line-height: 1.8; font-family: ${customFont}, sans-serif;">
                <div style="margin-bottom: 8px;">
                  <span style="font-weight: 600;">📌 เลขประจำตัวนักเรียน:</span> กรอก 5 หลัก เช่น 99999
                </div>
                <div style="margin-bottom: 8px;">
                  <span style="font-weight: 600;">🔐 รหัสผ่าน:</span> 305MEP69
                </div>
                <div style="margin-top: 12px; padding: 10px; background: #f3e8ff; border-radius: 8px; border-left: 3px solid #a855f7;">
                  <span style="font-weight: 600;">💡 เคล็ดลับ:</span> หากเข้าสู่ระบบไม่ได้ ให้ตรวจสอบว่ากรอกเลขประจำตัว 5 หลักถูกต้อง และใช้รหัสผ่านที่ครูแจ้ง
                </div>
              </div>
            </div>

            <form id="loginForm" style="display: flex; flex-direction: column; gap: 20px;">
              <div>
                <label for="studentId" style="display: block; font-size: ${baseSize * 0.9}px; font-weight: 600; color: ${textColor}; margin-bottom: 8px; font-family: ${customFont}, sans-serif;">
                  เลขประจำตัวนักเรียน (5 หลัก)
                </label>
                <input 
                  type="text" 
                  id="studentId" 
                  maxlength="5"
                  pattern="[0-9]{5}"
                  required
                  style="width: 100%; padding: 14px 18px; border: 2px solid #f3e8ff; border-radius: 12px; font-size: ${baseSize}px; color: ${textColor}; font-family: ${customFont}, sans-serif; box-sizing: border-box; transition: all 0.3s; background: #fffef5;"
                  placeholder="xxxxx"
                  onfocus="this.style.borderColor='${primaryColor}'; this.style.boxShadow='0 0 0 3px rgba(168, 85, 247, 0.1)'"
                  onblur="this.style.borderColor='#f3e8ff'; this.style.boxShadow='none'"
                >
              </div>

              <div>
                <label for="password" style="display: block; font-size: ${baseSize * 0.9}px; font-weight: 600; color: ${textColor}; margin-bottom: 8px; font-family: ${customFont}, sans-serif;">
                  รหัสผ่าน
                </label>
                <input 
                  type="password" 
                  id="password" 
                  required
                  style="width: 100%; padding: 14px 18px; border: 2px solid #f3e8ff; border-radius: 12px; font-size: ${baseSize}px; color: ${textColor}; font-family: ${customFont}, sans-serif; box-sizing: border-box; transition: all 0.3s; background: #fffef5;"
                  placeholder="กรอกรหัสผ่าน"
                  onfocus="this.style.borderColor='${primaryColor}'; this.style.boxShadow='0 0 0 3px rgba(168, 85, 247, 0.1)'"
                  onblur="this.style.borderColor='#f3e8ff'; this.style.boxShadow='none'"
                >
              </div>

              <div id="errorMessage" style="display: none; padding: 14px; background: linear-gradient(135deg, #fee2e2 0%, #fef0f7 100%); border-radius: 12px; color: #dc2626; font-size: ${baseSize * 0.9}px; font-family: ${customFont}, sans-serif; border: 2px solid #fca5a5;"></div>

              <button 
                type="submit"
                style="width: 100%; padding: 16px; background: linear-gradient(135deg, #f97316 0%, #9333ea 100%); color: white; border: none; border-radius: 12px; font-size: ${baseSize * 1.1}px; font-weight: 600; cursor: pointer; transition: all 0.3s; font-family: ${customFont}, sans-serif; box-shadow: 0 4px 16px rgba(249, 115, 22, 0.3);"
                onmouseover="this.style.transform='translateY(-2px)'; this.style.boxShadow='0 8px 24px rgba(249, 115, 22, 0.4)'"
                onmouseout="this.style.transform='translateY(0)'; this.style.boxShadow='0 4px 16px rgba(249, 115, 22, 0.3)'"
              >
                ✨ เข้าสู่ระบบ
              </button>
            </form>
          </div>
        </div>
      `;

      document.getElementById('loginForm').addEventListener('submit', handleLogin);
    }

    function handleLogin(e) {
      e.preventDefault();
      const studentId = document.getElementById('studentId').value;
      const password = document.getElementById('password').value;
      const errorDiv = document.getElementById('errorMessage');

      if (studentId.length !== 5 || !/^\d{5}$/.test(studentId)) {
        errorDiv.textContent = "❌ กรุณากรอกเลขประจำตัวนักเรียน 5 หลักให้ถูกต้อง";
        errorDiv.style.display = 'block';
        return;
      }

      if (password !== PASSWORD) {
        errorDiv.textContent = "❌ รหัสผ่านไม่ถูกต้อง";
        errorDiv.style.display = 'block';
        return;
      }

      if (!studentsData[studentId]) {
        errorDiv.textContent = "❌ ไม่พบข้อมูลนักเรียนในระบบ";
        errorDiv.style.display = 'block';
        return;
      }

      currentStudentId = studentId;
      renderScoresPage();
    }

    function renderScoresPage() {
      const config = window.elementSdk?.config || defaultConfig;
      const app = document.getElementById('app');
      const customFont = config.font_family || defaultConfig.font_family;
      const baseSize = config.font_size || defaultConfig.font_size;
      const cardColor = config.card_color || defaultConfig.card_color;
      const textColor = config.text_color || defaultConfig.text_color;
      const primaryColor = config.primary_color || defaultConfig.primary_color;
      const accentColor = config.accent_color || defaultConfig.accent_color;
      const schoolName = config.school_name || defaultConfig.school_name;
      const className = config.class_name || defaultConfig.class_name;
      const subjectName = config.subject_name || defaultConfig.subject_name;
      const teacherName = config.teacher_name || defaultConfig.teacher_name;

      const studentData = studentsData[currentStudentId];
      const chapter1Score = studentData.chapter1;
      const chapter2Score = studentData.chapter2;
      const chapter3Score = studentData.chapter3;
      const chapter4Score = studentData.chapter4;
      const chapter5Score = studentData.chapter5;
      const averageScore = "-";

      app.innerHTML = `
        <div class="h-full w-full" style="background: linear-gradient(135deg, #fef3e2 0%, #fbe8d3 50%, #fef3e2 100%); overflow-y: auto; position: relative;">
          <div style="position: fixed; top: 40px; left: 30px; font-size: 48px; opacity: 0.5; animation: float 3s ease-in-out infinite; pointer-events: none;">🍦</div>
          <div style="position: fixed; top: 150px; right: 50px; font-size: 44px; opacity: 0.55; animation: float 4s ease-in-out infinite; animation-delay: 1s; pointer-events: none;">🎀</div>
          <div style="position: fixed; bottom: 300px; left: 40px; font-size: 40px; opacity: 0.5; animation: float 3.5s ease-in-out infinite; animation-delay: 0.5s; pointer-events: none;">🍭</div>
          <div style="position: fixed; bottom: 400px; right: 60px; font-size: 42px; opacity: 0.55; animation: float 4.5s ease-in-out infinite; animation-delay: 1.5s; pointer-events: none;">🎀</div>
          <style>
            @keyframes float {
              0%, 100% { transform: translateY(0px); }
              50% { transform: translateY(-20px); }
            }
          </style>
          <div style="max-width: 900px; margin: 0 auto; padding: 32px 24px;">
            <div style="background: ${cardColor}; border-radius: 24px; padding: 36px; box-shadow: 0 8px 32px rgba(168, 85, 247, 0.15); margin-bottom: 28px; border: 3px solid rgba(168, 85, 247, 0.1);">
              <div style="display: flex; justify-content: space-between; align-items: center; flex-wrap: wrap; gap: 16px; margin-bottom: 20px; position: relative;">
                <div style="position: absolute; top: -20px; left: 10px; font-size: 28px;">🍭</div>
                <div style="position: absolute; top: -15px; right: 10px; font-size: 28px;">🍦</div>
                <div>
                  <div style="font-size: ${baseSize * 1.9}px; font-weight: 700; background: linear-gradient(135deg, #f97316 0%, #9333ea 50%, #a855f7 100%); -webkit-background-clip: text; -webkit-text-fill-color: transparent; background-clip: text; margin-bottom: 10px; font-family: ${customFont}, sans-serif;">
                    💖 คะแนนสอบเก็บคะแนน วิชาคณิตศาสตร์
                  </div>
                  <div style="font-size: ${baseSize * 1.05}px; font-weight: 600; color: ${textColor}; margin-bottom: 5px; font-family: ${customFont}, sans-serif;">
                    ${schoolName}
                  </div>
                  <div style="font-size: ${baseSize * 0.95}px; color: ${textColor}; opacity: 0.75; margin-bottom: 3px; font-family: ${customFont}, sans-serif;">
                    ${className}
                  </div>
                  <div style="font-size: ${baseSize * 0.9}px; color: ${textColor}; opacity: 0.7; margin-bottom: 5px; font-family: ${customFont}, sans-serif;">
                    ${subjectName}
                  </div>
                  <div style="font-size: ${baseSize * 0.95}px; font-weight: 700; color: ${textColor}; opacity: 0.85; font-family: ${customFont}, sans-serif;">
                    ครูผู้สอน ${teacherName}
                  </div>
                </div>
                <button 
                  id="logoutBtn"
                  style="padding: 12px 24px; background: white; color: #f97316; border: 2px solid #f97316; border-radius: 12px; font-size: ${baseSize * 0.9}px; font-weight: 600; cursor: pointer; font-family: ${customFont}, sans-serif; transition: all 0.3s;"
                  onmouseover="this.style.background='linear-gradient(135deg, #f97316 0%, #9333ea 100%)'; this.style.color='white'; this.style.transform='scale(1.05)'"
                  onmouseout="this.style.background='white'; this.style.color='#f97316'; this.style.transform='scale(1)'"
                >
                  👋 ออกจากระบบ
                </button>
              </div>
              <div style="padding: 20px; background: linear-gradient(135deg, #f97316 0%, #9333ea 50%, #a855f7 100%); border-radius: 16px; box-shadow: 0 4px 16px rgba(249, 115, 22, 0.3); margin-bottom: 16px;">
                <div style="font-size: ${baseSize * 0.9}px; color: white; opacity: 0.95; margin-bottom: 6px; font-family: ${customFont}, sans-serif;">
                  ⭐ เลขประจำตัวนักเรียน
                </div>
                <div style="font-size: ${baseSize * 1.6}px; font-weight: 700; color: white; font-family: ${customFont}, sans-serif;">
                  ${currentStudentId}
                </div>
              </div>
            </div>

            <div style="background: ${cardColor}; border-radius: 20px; padding: 28px; box-shadow: 0 6px 24px rgba(168, 85, 247, 0.1); border: 3px solid rgba(168, 85, 247, 0.2); position: relative;">
              <div style="position: absolute; top: -18px; left: 30px; font-size: 32px;">🎀</div>
              <div style="position: absolute; top: -18px; right: 30px; font-size: 32px;">🎀</div>
                  <div style="font-size: ${baseSize * 1.3}px; font-weight: 700; color: ${textColor}; margin-bottom: 24px; font-family: ${customFont}, sans-serif;">
                📊 คะแนนสอบรายบุคคล บทที่ 1 - บทที่ 5
              </div>
              ${true ? `
                <div style="display: flex; flex-wrap: wrap; gap: 20px; margin-bottom: 24px;">
                  <div style="flex: 1; padding: 16px; background: linear-gradient(135deg, #fed7aa 0%, #fde68a 100%); border-radius: 14px; border: 2px solid #f97316; text-align: center;">
                    <div style="font-size: ${baseSize * 0.85}px; font-weight: 600; color: #92400e; margin-bottom: 8px; font-family: ${customFont}, sans-serif;">
                      📚 บทที่ 1<br><span style="font-size: ${baseSize * 0.68}px; font-weight: 400;">${chapterTitles[0]}</span>
                    </div>
                    <div style="font-size: ${baseSize * 2.2}px; font-weight: 700; background: linear-gradient(135deg, #f97316 0%, #9333ea 100%); -webkit-background-clip: text; -webkit-text-fill-color: transparent; background-clip: text; font-family: ${customFont}, sans-serif;">
                      ${chapter1Score}
                    </div>
                    <div style="font-size: ${baseSize * 0.8}px; color: #92400e; font-family: ${customFont}, sans-serif;">
                      / ${MAX_SCORE}
                    </div>
                  </div>
                  <div style="flex: 1; padding: 16px; background: linear-gradient(135deg, #e9d5ff 0%, #f3e8ff 100%); border-radius: 14px; border: 2px solid #9333ea; text-align: center;">
                    <div style="font-size: ${baseSize * 0.85}px; font-weight: 600; color: #6b21a8; margin-bottom: 8px; font-family: ${customFont}, sans-serif;">
                      📚 บทที่ 2<br><span style="font-size: ${baseSize * 0.68}px; font-weight: 400;">${chapterTitles[1]}</span>
                    </div>
                    <div style="font-size: ${baseSize * 2.2}px; font-weight: 700; background: linear-gradient(135deg, #f97316 0%, #9333ea 100%); -webkit-background-clip: text; -webkit-text-fill-color: transparent; background-clip: text; font-family: ${customFont}, sans-serif;">
                      ${chapter2Score}
                    </div>
                    <div style="font-size: ${baseSize * 0.8}px; color: #6b21a8; font-family: ${customFont}, sans-serif;">
                      / ${MAX_SCORE}
                    </div>
                  </div>
                  ${[
                    [`บทที่ 3<br><span style="font-size:${baseSize * 0.68}px; font-weight:400;">${chapterTitles[2]}</span>`, chapter3Score, '#dcfce7', '#16a34a', '#166534'],
                    [`บทที่ 4<br><span style="font-size:${baseSize * 0.68}px; font-weight:400;">${chapterTitles[3]}</span>`, chapter4Score, '#dbeafe', '#2563eb', '#1e40af'],
                    [`บทที่ 5<br><span style="font-size:${baseSize * 0.68}px; font-weight:400;">${chapterTitles[4]}</span>`, chapter5Score, '#fce7f3', '#db2777', '#9d174d']
                  ].map(([title, score, bg, border, label]) => `
                    <div style="flex: 1; min-width: 140px; padding: 16px; background: ${bg}; border-radius: 14px; border: 2px solid ${border}; text-align: center;">
                      <div style="font-size: ${baseSize * 0.85}px; font-weight: 600; color: ${label}; margin-bottom: 8px; font-family: ${customFont}, sans-serif;">📚 ${title}</div>
                      <div style="font-size: ${baseSize * 1.75}px; font-weight: 700; color: ${label}; font-family: ${customFont}, sans-serif;">${score}</div>
                      <div style="font-size: ${baseSize * 0.8}px; color: ${label}; font-family: ${customFont}, sans-serif;">${score === 'ขาดสอบ' ? '' : '/ ' + MAX_SCORE}</div>
                    </div>
                  `).join('')}
                </div>

                <div style="background: linear-gradient(135deg, #fffef5 0%, #f5f3f0 100%); border-radius: 16px; padding: 24px; border: 2px solid rgba(168, 85, 247, 0.15); height: 360px;">
                  <div style="font-size: ${baseSize * 0.95}px; font-weight: 600; color: ${textColor}; margin-bottom: 16px; font-family: ${customFont}, sans-serif;">
                    📊 แผนภูมิคะแนนสอบทั้ง 5 บท
                  </div>
                  <div id="scoresChart" style="height: 100%; width: 100%;"></div>
                </div>

              ` : `
                <div style="padding: 40px 0; text-align: center;">
                  <div style="font-size: ${baseSize * 2.5}px; margin-bottom: 12px;">😢</div>
                  <div style="font-size: ${baseSize * 1.3}px; font-weight: 700; color: #dc2626; font-family: ${customFont}, sans-serif;">
                    ขาดสอบ
                  </div>
                </div>
              `}
            </div>
          </div>
        </div>
      `;

      document.getElementById('logoutBtn').addEventListener('click', () => {
        currentStudentId = null;
        renderLoginPage();
      });

      // Render one chart for all five chapters
      renderChart([chapter1Score, chapter2Score, chapter3Score, chapter4Score, chapter5Score], customFont, baseSize);
    }

    function renderChart(scores, customFont, baseSize) {
      const chartContainer = document.getElementById('scoresChart');
      if (!chartContainer) return;

      const labels = ['บทที่ 1', 'บทที่ 2', 'บทที่ 3', 'บทที่ 4', 'บทที่ 5'];
      const chartTitles = chapterTitles;
      const fields = ['chapter1', 'chapter2', 'chapter3', 'chapter4', 'chapter5'];
      const colors = ['#f97316', '#9333ea', '#16a34a', '#2563eb', '#db2777'];
      const validScores = scores.map(score => typeof score === 'number' ? score : 0);
      const total = scores.filter(score => typeof score === 'number').reduce((sum, score) => sum + score, 0);
      const average = scores.some(score => typeof score !== 'number') ? '-' : (total / scores.length).toFixed(1);
      const topStudents = fields.map(field => Object.entries(studentsData)
        .filter(([, student]) => typeof student[field] === 'number')
        .sort((a, b) => b[1][field] - a[1][field])[0]);
      const lowestScores = fields.map(field => Object.values(studentsData)
        .filter(student => typeof student[field] === 'number')
        .reduce((lowest, student) => Math.min(lowest, student[field]), MAX_SCORE));

      chartContainer.innerHTML = `
        <div style="height:100%; display:flex; flex-direction:column; gap:12px; font-family:${customFont}, sans-serif;">
          <div style="display:flex; justify-content:space-between; align-items:center; flex-wrap:wrap; gap:8px; color:#7c2d12; font-size:${baseSize * 0.9}px;">
            <span>📈 คะแนนของฉัน เทียบกับคะแนนสูงสุดและต่ำสุดของห้อง</span>
            <strong style="color:#9333ea;">ค่าเฉลี่ย ${average}</strong>
          </div>
          <div style="display:flex; justify-content:center; gap:18px; flex-wrap:wrap; font-size:${baseSize * 0.76}px; color:#7c2d12;">
            <span><b style="display:inline-block; width:12px; height:12px; border-radius:3px; background:#f97316; margin-right:5px;"></b>คะแนนของฉัน</span>
            <span><b style="display:inline-block; width:12px; height:12px; border-radius:3px; background:#facc15; margin-right:5px;"></b>คะแนนสูงสุด</span>
            <span><b style="display:inline-block; width:12px; height:12px; border-radius:3px; background:#64748b; margin-right:5px;"></b>คะแนนต่ำสุด</span>
          </div>
          <div style="flex:1; display:flex; align-items:flex-end; justify-content:space-around; gap:8px; padding:18px 4px 4px; border-bottom:2px solid #e9d5ff; background:linear-gradient(180deg, rgba(243,232,255,.35), rgba(255,254,245,.3)); border-radius:14px 14px 4px 4px;">
            ${validScores.map((score, index) => {
              const topScore = topStudents[index] ? topStudents[index][1][fields[index]] : 0;
              const lowestScore = lowestScores[index];
              const myHeight = Math.max(8, (score / MAX_SCORE) * 100);
              const topHeight = Math.max(8, (topScore / MAX_SCORE) * 100);
              const lowestHeight = Math.max(8, (lowestScore / MAX_SCORE) * 100);
              const isAbsent = scores[index] === 'ขาดสอบ';
              const topName = topStudents[index] ? topStudents[index][1].name : '-';
              return `<div style="height:100%; flex:1; max-width:130px; display:flex; flex-direction:column; align-items:center; justify-content:flex-end; gap:5px;">
                <div style="font-size:${baseSize * 0.68}px; color:#92400e; text-align:center; line-height:1.25; min-height:32px;">สูงสุด ${topScore}<br><span style="font-size:${baseSize * 0.58}px;">${topName}</span></div>
                <div style="height:58%; width:100%; display:flex; align-items:flex-end; justify-content:center; gap:4px;">
                  <div title="${labels[index]} คะแนนของฉัน: ${isAbsent ? 'ขาดสอบ' : score}" style="width:22%; height:${myHeight}%; min-height:8px; background:${colors[index]}; border-radius:7px 7px 2px 2px; box-shadow:0 4px 9px ${colors[index]}55;"></div>
                  <div title="${labels[index]} คะแนนสูงสุด: ${topScore} (${topName})" style="width:22%; height:${topHeight}%; min-height:8px; background:#facc15; border:2px solid #eab308; border-radius:7px 7px 2px 2px; box-shadow:0 4px 9px rgba(234,179,8,.25);"></div>
                  <div title="${labels[index]} คะแนนต่ำสุดของห้อง: ${lowestScore}" style="width:22%; height:${lowestHeight}%; min-height:8px; background:#64748b; border:2px solid #475569; border-radius:7px 7px 2px 2px; box-shadow:0 4px 9px rgba(71,85,105,.25);"></div>
                </div>
                <div style="font-size:${baseSize * 0.78}px; font-weight:700; color:#7c2d12; text-align:center;">${labels[index]}</div>
                <div style="font-size:${baseSize * 0.62}px; color:#92400e; text-align:center; line-height:1.25; max-width:150px;">${chartTitles[index]}</div>
                <div style="font-size:${baseSize * 0.68}px; color:#7c2d12;">${isAbsent ? 'ขาดสอบ' : score} / ${topScore} / ${lowestScore}</div>
              </div>`;
            }).join('')}
          </div>
          <div style="text-align:center; font-size:${baseSize * 0.68}px; color:#92400e;">แถบสีเหลืองคือคะแนนสูงสุดของนักเรียนในแต่ละบท</div>
        </div>`;
      return;
      
      // Get all scores and sort by average (lowest to highest)
      const allStudents = Object.entries(studentsData).map(([id, data]) => {
        const avg = (data.chapter1 + data.chapter2) / 2;
        return {
          id,
          name: data.name,
          chapter1: data.chapter1,
          chapter2: data.chapter2,
          average: avg
        };
      }).sort((a, b) => a.average - b.average);

      // Add animation styles
      const style = document.createElement('style');
      style.textContent = `
        @keyframes draw {
          from { stroke-dashoffset: 1000; }
          to { stroke-dashoffset: 0; }
        }
      `;
      document.head.appendChild(style);
      
      const padding = 40;
      const width = chartContainer.clientWidth - padding * 2;
      const height = chartContainer.clientHeight - padding * 2;
      
      // Create SVG for line chart
      const svg = document.createElementNS('http://www.w3.org/2000/svg', 'svg');
      svg.setAttribute('width', '100%');
      svg.setAttribute('height', '100%');
      svg.setAttribute('viewBox', `0 0 ${chartContainer.clientWidth} ${chartContainer.clientHeight}`);
      svg.setAttribute('style', 'overflow: visible;');
      
      const maxScore = MAX_SCORE;
      
      // Draw grid lines and labels (0, 1, 2, 3, ..., 20)
      for (let score = 0; score <= 20; score += 1) {
        const y = padding + height - (score / maxScore) * height;
        const line = document.createElementNS('http://www.w3.org/2000/svg', 'line');
        line.setAttribute('x1', padding);
        line.setAttribute('y1', y);
        line.setAttribute('x2', chartContainer.clientWidth - padding);
        line.setAttribute('y2', y);
        line.setAttribute('stroke', '#e0e0e0');
        line.setAttribute('stroke-width', '1');
        svg.appendChild(line);
        
        // Score labels (0, 2, 4, 6, 8, 10, 12, 14, 16, 18, 20)
        const scoreLabel = document.createElementNS('http://www.w3.org/2000/svg', 'text');
        scoreLabel.setAttribute('x', padding - 8);
        scoreLabel.setAttribute('y', y + 4);
        scoreLabel.setAttribute('text-anchor', 'end');
        scoreLabel.setAttribute('font-size', baseSize * 0.7);
        scoreLabel.setAttribute('fill', '#999');
        scoreLabel.textContent = score.toFixed(0);
        svg.appendChild(scoreLabel);
      }
      
      // Draw lines for Chapter 1 and Chapter 2
      const pointRadius = 6;
      const pointSpacing = width / (allStudents.length - 1 || 1);
      
      // Chapter 1 line
      let chapter1Path = `M ${padding} ${padding + height - (allStudents[0].chapter1 / maxScore) * height}`;
      allStudents.forEach((student, index) => {
        const x = padding + (index * pointSpacing);
        const y = padding + height - (student.chapter1 / maxScore) * height;
        chapter1Path += ` L ${x} ${y}`;
      });
      
      const chapter1Line = document.createElementNS('http://www.w3.org/2000/svg', 'path');
      chapter1Line.setAttribute('d', chapter1Path);
      chapter1Line.setAttribute('stroke', '#f97316');
      chapter1Line.setAttribute('stroke-width', '2.5');
      chapter1Line.setAttribute('fill', 'none');
      chapter1Line.setAttribute('stroke-linecap', 'round');
      chapter1Line.setAttribute('stroke-linejoin', 'round');
      svg.appendChild(chapter1Line);
      
      // Chapter 2 line
      let chapter2Path = `M ${padding} ${padding + height - (allStudents[0].chapter2 / maxScore) * height}`;
      allStudents.forEach((student, index) => {
        const x = padding + (index * pointSpacing);
        const y = padding + height - (student.chapter2 / maxScore) * height;
        chapter2Path += ` L ${x} ${y}`;
      });
      
      const chapter2Line = document.createElementNS('http://www.w3.org/2000/svg', 'path');
      chapter2Line.setAttribute('d', chapter2Path);
      chapter2Line.setAttribute('stroke', '#9333ea');
      chapter2Line.setAttribute('stroke-width', '2.5');
      chapter2Line.setAttribute('fill', 'none');
      chapter2Line.setAttribute('stroke-linecap', 'round');
      chapter2Line.setAttribute('stroke-linejoin', 'round');
      svg.appendChild(chapter2Line);
      
      // Draw points with stars for current student
      allStudents.forEach((student, index) => {
        const x = padding + (index * pointSpacing);
        
        // Chapter 1 point
        const ch1Y = padding + height - (student.chapter1 / maxScore) * height;
        const circle1 = document.createElementNS('http://www.w3.org/2000/svg', 'circle');
        circle1.setAttribute('cx', x);
        circle1.setAttribute('cy', ch1Y);
        circle1.setAttribute('r', '4');
        circle1.setAttribute('fill', '#f97316');
        circle1.setAttribute('stroke', 'white');
        circle1.setAttribute('stroke-width', '2');
        svg.appendChild(circle1);
        
        // Chapter 2 point
        const ch2Y = padding + height - (student.chapter2 / maxScore) * height;
        const circle2 = document.createElementNS('http://www.w3.org/2000/svg', 'circle');
        circle2.setAttribute('cx', x);
        circle2.setAttribute('cy', ch2Y);
        circle2.setAttribute('r', '4');
        circle2.setAttribute('fill', '#9333ea');
        circle2.setAttribute('stroke', 'white');
        circle2.setAttribute('stroke-width', '2');
        svg.appendChild(circle2);
        
        // Add star if current student
        if (student.id === currentStudentId) {
          const star1 = document.createElementNS('http://www.w3.org/2000/svg', 'text');
          star1.setAttribute('x', x);
          star1.setAttribute('y', ch1Y - 14);
          star1.setAttribute('text-anchor', 'middle');
          star1.setAttribute('font-size', '16');
          star1.textContent = '⭐';
          svg.appendChild(star1);
          
          const star2 = document.createElementNS('http://www.w3.org/2000/svg', 'text');
          star2.setAttribute('x', x);
          star2.setAttribute('y', ch2Y - 14);
          star2.setAttribute('text-anchor', 'middle');
          star2.setAttribute('font-size', '16');
          star2.textContent = '⭐';
          svg.appendChild(star2);
        }
      });
      
      // Add legend
      const legend = document.createElementNS('http://www.w3.org/2000/svg', 'g');
      
      const leg1Rect = document.createElementNS('http://www.w3.org/2000/svg', 'rect');
      leg1Rect.setAttribute('x', padding + 10);
      leg1Rect.setAttribute('y', chartContainer.clientHeight - 20);
      leg1Rect.setAttribute('width', '12');
      leg1Rect.setAttribute('height', '12');
      leg1Rect.setAttribute('fill', '#f97316');
      leg1Rect.setAttribute('rx', '2');
      legend.appendChild(leg1Rect);
      
      const leg1Text = document.createElementNS('http://www.w3.org/2000/svg', 'text');
      leg1Text.setAttribute('x', padding + 28);
      leg1Text.setAttribute('y', chartContainer.clientHeight - 10);
      leg1Text.setAttribute('font-size', baseSize * 0.8);
      leg1Text.setAttribute('fill', '#666');
      leg1Text.textContent = 'บทที่ 1';
      legend.appendChild(leg1Text);
      
      const leg2Rect = document.createElementNS('http://www.w3.org/2000/svg', 'rect');
      leg2Rect.setAttribute('x', padding + 110);
      leg2Rect.setAttribute('y', chartContainer.clientHeight - 20);
      leg2Rect.setAttribute('width', '12');
      leg2Rect.setAttribute('height', '12');
      leg2Rect.setAttribute('fill', '#9333ea');
      leg2Rect.setAttribute('rx', '2');
      legend.appendChild(leg2Rect);
      
      const leg2Text = document.createElementNS('http://www.w3.org/2000/svg', 'text');
      leg2Text.setAttribute('x', padding + 128);
      leg2Text.setAttribute('y', chartContainer.clientHeight - 10);
      leg2Text.setAttribute('font-size', baseSize * 0.8);
      leg2Text.setAttribute('fill', '#666');
      leg2Text.textContent = 'บทที่ 2';
      legend.appendChild(leg2Text);
      
      svg.appendChild(legend);
      
      chartContainer.appendChild(svg);
    }

    initApp();
  </script>
 </body>
</html>
