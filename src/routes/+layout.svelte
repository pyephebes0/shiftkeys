<script>
  // ถ้ามีอะไรในอนาคต เช่น คลิกเมนู เลื่อนลง ฯลฯ จะเขียนโค้ด JS ตรงนี้ได้
</script>

<header>
  <div class="container">
    <h1><a href="/">ShiftKeys</a></h1>
    <nav>
      <ul>
        <li><a href="/">หน้าแรก</a></li>
        <li><a href="#features">ฟีเจอร์</a></li>
        <li><a href="#howto">วิธีใช้งาน</a></li>
        <li><a href="#contact">ติดต่อเรา</a></li>
      </ul>
    </nav>
  </div>
</header>

<main>
  <slot></slot>
</main>

<style>
  header {
    width: 100%;
    background-color: #fff;
    box-shadow: 0 2px 8px rgba(0, 0, 0, 0.08);
    padding: 1.5rem 0;
    position: sticky;
    top: 0;
    z-index: 999;
    backdrop-filter: blur(8px);
  }

  .container {
    max-width: 1400px;
    margin: 0 auto;
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 0 2rem;
  }

  header h1 a {
    text-decoration: none;
    color: #111;
    font-size: 2.4rem;
    font-weight: 800; /* หนักแน่นขึ้น */
    font-family: 'Inter', 'Segoe UI', 'Roboto', sans-serif;
    letter-spacing: -0.8px;
    transition: color 0.3s ease;
  }

  header h1 a:hover {
    color: #0070f3;
  }

  nav ul {
    list-style: none;
    display: flex;
    gap: 2.5rem;
    margin: 0;
    padding: 0;
  }

  nav ul li a {
    text-decoration: none;
    color: #333;
    font-weight: 600;
    font-size: 1.1rem;
    font-family: 'Inter', 'Segoe UI', 'Roboto', sans-serif;
    position: relative;
    transition: color 0.3s ease;
  }

  /* เพิ่ม hover */
  nav ul li a::after {
    content: '';
    position: absolute;
    width: 0%;
    height: 2px;
    bottom: -4px;
    left: 0;
    background-color: #0070f3;
    transition: width 0.3s ease;
  }

  nav ul li a:hover {
    color: #0070f3;
  }

  nav ul li a:hover::after {
    width: 100%;
  }
</style>