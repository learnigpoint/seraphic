<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <meta name="description" content="Prakash Gautam | Seraphic Moments - Sharing inspiration, creativity, and personal experiences." />
  <title>Prakash Gautam | Seraphic Moments</title>
  <link rel="icon" href="https://cdn-icons-png.flaticon.com/512/3135/3135715.png" type="image/png" />
  <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.3/dist/css/bootstrap.min.css" rel="stylesheet" />
  <style>
    body {
      font-family: 'Segoe UI', sans-serif;
      background-color: #f8f9fa;
      color: #212529;
      transition: background-color 0.3s, color 0.3s;
    }
    header {
      background: linear-gradient(to right, #0d6efd, #0b5ed7);
      padding: 80px 0;
      color: #fff;
      text-align: center;
    }
    header h1 { font-size: 3rem; font-weight: 700; }
    header h2 { font-size: 1.3rem; font-weight: 300; margin-bottom: 20px; }
    .btn-main {
      background-color: #ffc107; color: #000; padding: 12px 30px; font-size: 1rem;
      border: none; border-radius: 5px; transition: 0.3s;
    }
    .btn-main:hover { background-color: #e0a800; }
    section { padding: 60px 0; }
    .service-box {
      background: #fff; border-radius: 10px; box-shadow: 0 0 15px rgba(0,0,0,0.05);
      padding: 30px; transition: transform 0.3s ease;
    }
    .service-box:hover { transform: translateY(-5px); }
    footer {
      text-align: center; padding: 25px 0; background: #e9ecef; color: #495057; margin-top: 40px;
    }
    /* Dark Mode */
    body.dark-mode { background-color: #121212; color: #e9ecef; }
    body.dark-mode header { background: linear-gradient(to right, #212529, #343a40); }
    body.dark-mode .service-box { background: #1e1e1e; color: #e9ecef; box-shadow: 0 0 15px rgba(255,255,255,0.05); }
    body.dark-mode footer { background: #1e1e1e; color: #bbb; }
    body.dark-mode #previewImage { border: 2px solid #fff; }
    .dark-toggle-btn {
      position: fixed; top: 15px; right: 15px;
      background-color: #0d6efd; color: white; border: none;
      padding: 8px 12px; border-radius: 5px; cursor: pointer; z-index: 1000;
    }
    .dark-toggle-btn:hover { background-color: #0b5ed7; }
  </style>
</head>
<body>

  <!-- Dark Mode Toggle -->
  <button id="darkToggle" class="dark-toggle-btn">🌙 Dark Mode</button>

  <!-- Hero Section -->
  <header>
    <div class="container">
      <h1>Prakash Gautam</h1>
      <h2>Seraphic Moments | Inspiring Through Creativity</h2>
      <a href="#contact" class="btn btn-main">Let's Connect</a>
    </div>
  </header>

  <!-- Photo Upload Section -->
  <section id="upload" class="text-center bg-light">
    <div class="container">
      <h3 class="mb-3">Upload Your Photo</h3>
      <p>Select an image file to preview below.</p>
      <input type="file" id="photoInput" accept="image/*" class="form-control mb-3" style="max-width:400px; margin:auto;">
      <div>
        <img id="previewImage" src="" alt="Preview will appear here" style="max-width: 300px; display:none; border-radius:10px; margin-top:20px;">
      </div>
    </div>
  </section>

  <!-- About Section -->
  <section id="about" class="text-center">
    <div class="container">
      <h3 class="mb-4">About Me</h3>
      <p class="lead">
        I am here to support your journey towards mastering knowledge and achieving career success. 
        Through Seraphic Moments, I share ideas, inspiration, and life’s beautiful experiences.
      </p>
    </div>
  </section>

  <!-- Services Section -->
  <section id="services" class="bg-light text-center">
    <div class="container">
      <h3 class="mb-5">What I Share</h3>
      <div class="row">
        <div class="col-md-4">
          <div class="service-box">
            <h5>Motivational Thoughts</h5>
            <p>Words that inspire and encourage positive thinking in everyday life.</p>
          </div>
        </div>
        <div class="col-md-4">
          <div class="service-box">
            <h5>Life Experiences</h5>
            <p>Sharing real stories and lessons to inspire and guide others.</p>
          </div>
        </div>
        <div class="col-md-4">
          <div class="service-box">
            <h5>Creative Ideas</h5>
            <p>Unique and thoughtful concepts to spark creativity in all aspects of life.</p>
          </div>
        </div>
      </div>
    </div>
  </section>

  <!-- Contact -->
  <section id="contact" class="text-center">
    <div class="container">
      <h3 class="mb-3">Let's Connect</h3>
      <p>Feel free to reach out via Instagram.</p>
      <a href="https://www.instagram.com/prakashgautam00?igsh=MTE1dTQzMGRyeXZ4dw" target="_blank" rel="noopener noreferrer" class="btn btn-main">
        Message Me on Instagram
      </a>
    </div>
  </section>

  <!-- Footer -->
  <footer>
    <p>&copy; 2025 Prakash Gautam | Seraphic Moments</p>
  </footer>

  <!-- Scripts -->
  <script>
    // Dark Mode Toggle
    const toggleBtn = document.getElementById('darkToggle');
    const body = document.body;
    if (localStorage.getItem('dark-mode') === 'enabled') {
      body.classList.add('dark-mode');
      toggleBtn.textContent = '☀️ Light Mode';
    }
    toggleBtn.addEventListener('click', () => {
      body.classList.toggle('dark-mode');
      if (body.classList.contains('dark-mode')) {
        localStorage.setItem('dark-mode', 'enabled');
        toggleBtn.textContent = '☀️ Light Mode';
      } else {
        localStorage.setItem('dark-mode', 'disabled');
        toggleBtn.textContent = '🌙 Dark Mode';
      }
    });

    // Photo Upload Preview
    const photoInput = document.getElementById('photoInput');
    const previewImage = document.getElementById('previewImage');
    photoInput.addEventListener('change', function() {
      const file = this.files[0];
      if (file) {
        const reader = new FileReader();
        reader.onload = function(e) {
          previewImage.src = e.target.result;
          previewImage.style.display = 'block';
        }
        reader.readAsDataURL(file);
      } else {
        previewImage.style.display = 'none';
      }
    });
  </script>

</body>
</html>
