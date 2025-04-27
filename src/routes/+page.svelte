<script>
  export const prerender = true;

  let inputText = '';
  let outputText = '';

  const mapEngToThai = {
    '`': '_', '1': 'ๅ', '2': '/', '3': '-', '4': 'ภ', '5': 'ถ', '6': 'ุ', '7': 'ึ', '8': 'ค', '9': 'ต', '0': 'จ', '-': 'ข', '=': 'ช',
    'q': 'ๆ', 'w': 'ไ', 'e': 'ำ', 'r': 'พ', 't': 'ะ', 'y': 'ั', 'u': 'ี', 'i': 'ร', 'o': 'น', 'p': 'ย', '[': 'บ', ']': 'ล', '\\': 'ฃ',
    'a': 'ฟ', 's': 'ห', 'd': 'ก', 'f': 'ด', 'g': 'เ', 'h': '้', 'j': '่', 'k': 'า', 'l': 'ส', ';': 'ว', "'": 'ง',
    'z': 'ผ', 'x': 'ป', 'c': 'แ', 'v': 'อ', 'b': 'ิ', 'n': 'ื', 'm': 'ท', ',': 'ม', '.': 'ใ', '/': 'ฝ'
  };

  function convertText(text) {
    return text.split('').map(char => mapEngToThai[char] || char).join('');
  }

  $: outputText = convertText(inputText);
</script>

<svelte:head>
  <title>ShiftKeys - แปลงคีย์บอร์ดอังกฤษเป็นภาษาไทยออนไลน์ ใช้งานฟรี</title>
  <meta name="description" content="ShiftKeys เครื่องมือออนไลน์สำหรับแปลงข้อความจากคีย์บอร์ดภาษาอังกฤษเป็นภาษาไทย อัตโนมัติ ฟรี ใช้งานง่าย รองรับมือถือและคอมพิวเตอร์" />
  <meta name="keywords" content="แปลงภาษาอังกฤษเป็นไทย, แปลงคีย์บอร์ดอังกฤษไทย, โปรแกรมแปลงภาษา, พิมพ์อังกฤษเป็นไทย, ShiftKeys" />
  <meta name="author" content="ShiftKeys Team" />
  <meta name="robots" content="index, follow" />
  <link rel="canonical" href="https://yourdomain.com/" /> <!-- เปลี่ยน yourdomain.com ตามจริง -->

  <!-- OpenGraph / Facebook -->
  <meta property="og:type" content="website" />
  <meta property="og:url" content="https://yourdomain.com/" />
  <meta property="og:title" content="ShiftKeys - แปลงคีย์บอร์ดอังกฤษเป็นไทยออนไลน์ ใช้งานฟรี" />
  <meta property="og:description" content="ShiftKeys ช่วยแปลงข้อความจากคีย์บอร์ดอังกฤษเป็นไทยได้ง่าย ๆ ออนไลน์ 100%" />
  <meta property="og:image" content="https://yourdomain.com/your-og-image.png" /> <!-- ใส่ลิงก์โลโก้หรือรูปโปรโมท -->

  <!-- Twitter Card -->
  <meta name="twitter:card" content="summary_large_image" />
  <meta name="twitter:url" content="https://yourdomain.com/" />
  <meta name="twitter:title" content="ShiftKeys - แปลงคีย์บอร์ดอังกฤษเป็นไทยออนไลน์ ใช้งานฟรี" />
  <meta name="twitter:description" content="ShiftKeys เครื่องมือออนไลน์ แปลงภาษาอังกฤษเป็นไทย ใช้งานฟรี รองรับทุกอุปกรณ์" />
  <meta name="twitter:image" content="https://yourdomain.com/your-og-image.png" />
  
  <!-- Favicon -->
  <link rel="icon" href="/favicon.ico" type="image/x-icon" />
</svelte:head>

<main>
  <h1>แปลงภาษาอังกฤษเป็นไทยแบบเรียลไทม์</h1>
  <textarea
    bind:value={inputText}
    placeholder="พิมพ์ภาษาอังกฤษที่นี่..."
  ></textarea>

  <div class="output">
    {outputText}
  </div>
</main>

<style>
  main {
    min-height: 60vh;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    background: #f9fafb;
    padding: 20px;
    box-sizing: border-box;
  }

  h1 {
    font-size: 32px;
    color: #222;
    margin-bottom: 30px;
    font-family: 'Inter', 'Noto Sans Thai', 'Prompt', sans-serif;
    text-align: center;
  }

  textarea {
    width: 100%;
    max-width: 600px;
    height: 160px;
    padding: 16px;
    font-size: 18px;
    border: 1px solid #ddd;
    border-radius: 12px;
    background: #fff;
    box-shadow: 0 2px 6px rgba(0, 0, 0, 0.04);
    resize: none;
    margin-bottom: 24px;
    font-family: 'Noto Sans Thai', 'Prompt', sans-serif;
    transition: border 0.3s, box-shadow 0.3s;
  }

  textarea:focus {
    outline: none;
    border-color: #60a5fa;
    box-shadow: 0 0 0 3px rgba(96, 165, 250, 0.4);
  }

  .output {
    width: 100%;
    max-width: 600px;
    min-height: 160px;
    padding: 16px;
    font-size: 18px;
    border: 1px solid #ddd;
    border-radius: 12px;
    background: #fff;
    box-shadow: 0 2px 6px rgba(0, 0, 0, 0.04);
    color: #333;
    font-family: 'Noto Sans Thai', 'Prompt', sans-serif;
    white-space: pre-wrap;
    word-break: break-word;
  }
</style>
