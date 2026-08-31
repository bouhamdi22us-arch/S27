<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Samsung Galaxy S27 - Next Gen Experience</title>
  <script src="https://cdn.tailwindcss.com"></script>
  <script src="https://cdnjs.cloudflare.com/ajax/libs/gsap/3.12.2/gsap.min.js"></script>
  <script src="https://cdnjs.cloudflare.com/ajax/libs/three.js/r128/three.min.js"></script>
  
  <style>
    body {
      background-color: #030308;
      color: #f3f4f6;
      font-family: system-ui, -apple-system, sans-serif;
      overflow-x: hidden;
    }
    /* Glows y Neón estilo Samsung */
    .glow-cyan {
      box-shadow: 0 0 25px rgba(6, 182, 212, 0.4);
    }
    .glow-purple {
      box-shadow: 0 0 25px rgba(168, 85, 247, 0.4);
    }
    .glass {
      background: rgba(255, 255, 255, 0.03);
      backdrop-filter: blur(16px);
      border: 1px solid rgba(255, 255, 255, 0.08);
    }
    /* Ocultar secciones no activas para routing SPA */
    .page {
      display: none;
      opacity: 0;
    }
    .page.active {
      display: block;
    }
  </style>
</head>
<body class="relative min-h-screen flex flex-col justify-between">

  <canvas id="bg-canvas" class="fixed top-0 left-0 w-full h-full -z-10 pointer-events-none"></canvas>

  <header class="fixed top-0 left-0 w-full z-50 p-6">
    <nav class="max-w-6xl mx-auto glass rounded-full px-8 py-4 flex justify-between items-center border-emerald-500/20">
      <div class="text-2xl font-black tracking-widest text-transparent bg-clip-text bg-gradient-to-r from-cyan-400 to-purple-500">
        SAMSUNG S27
      </div>
      
      <ul class="flex space-x-8 text-sm font-semibold tracking-wide">
        <li><button onclick="navigateTo('home')" class="nav-btn text-cyan-400 hover:text-white transition">INICIO</button></li>
        <li><button onclick="navigateTo('specs')" class="nav-btn text-gray-400 hover:text-white transition">POTENCIA</button></li>
        <li><button onclick="navigateTo('camera')" class="nav-btn text-gray-400 hover:text-white transition">CÁMARA AI</button></li>
        <li><button onclick="navigateTo('design')" class="nav-btn text-gray-400 hover:text-white transition">DISEÑO 3D</button></li>
      </ul>

      <button class="bg-gradient-to-r from-cyan-500 to-blue-600 px-6 py-2 rounded-full font-bold text-xs tracking-wider glow-cyan hover:scale-105 transition transform">
        RESERVAR
      </button>
    </nav>
  </header>

  <main class="pt-32 pb-20 px-6 max-w-6xl mx-auto w-full flex-grow flex items-center justify-center">

    <section id="page-home" class="page active w-full">
      <div class="grid md:grid-cols-2 gap-12 items-center">
        <div class="space-y-6" id="home-text">
          <span class="text-cyan-400 text-xs font-bold tracking-widest uppercase bg-cyan-950/50 px-4 py-2 rounded-full border border-cyan-800/50">
            El futuro del rendimiento móvil
          </span>
          <h1 class="text-6xl font-black leading-tight">
            Samsung Galaxy <br>
            <span class="text-transparent bg-clip-text bg-gradient-to-r from-cyan-400 via-purple-400 to-pink-500">
              S27 Ultra
            </span>
          </h1>
          <p class="text-gray-400 text-lg">
            Redefiniendo la interacción fluida con respuesta hápitca avanzada, pantalla cuántica de 144Hz y procesador Neural Exynos 4nm.
          </p>
          <div class="flex space-x-4 pt-4">
            <button onclick="navigateTo('specs')" class="bg-white text-black font-bold px-8 py-4 rounded-2xl hover:bg-cyan-400 transition transform hover:-translate-y-1">
              Explorar características
            </button>
            <button onclick="navigateTo('design')" class="glass border border-white/20 px-8 py-4 rounded-2xl font-bold hover:bg-white/10 transition">
              Ver modelo 3D
            </button>
          </div>
        </div>
        
        <div class="relative flex justify-center items-center">
          <div id="phone-card" class="w-72 h-[500px] glass rounded-[40px] p-6 border border-white/20 flex flex-col justify-between glow-purple relative overflow-hidden group cursor-pointer">
            <div class="w-20 h-4 bg-black/60 rounded-full mx-auto mb-4"></div>
            <div class="text-center my-auto">
              <span class="text-5xl font-extrabold text-white/20 group-hover:text-cyan-400 transition duration-500">S27</span>
              <p class="text-xs text-gray-500 mt-2">Pasa el cursor para interactuar</p>
            </div>
            <div class="bg-cyan-500/20 p-4 rounded-2xl border border-cyan-500/30">
              <p class="text-xs font-mono text-cyan-300">Batería Cuántica: 100%</p>
            </div>
          </div>
        </div>
      </div>
    </section>

    <section id="page-specs" class="page w-full">
      <h2 class="text-4xl font-bold text-center mb-12">Especificaciones de Nueva Generación</h2>
      <div class="grid md:grid-cols-3 gap-8">
        <div class="glass p-8 rounded-3xl hover:border-cyan-500 transition duration-300 spec-card">
          <div class="text-3xl text-cyan-400 mb-4">⚡</div>
          <h3 class="text-xl font-bold mb-2">Chip Neural Snapdragon 8 Gen 6</h3>
          <p class="text-gray-400 text-sm">Capaz de ejecutar modelos de lenguaje complejos directamente en el dispositivo en milisegundos.</p>
        </div>
        <div class="glass p-8 rounded-3xl hover:border-purple-500 transition duration-300 spec-card">
          <div class="text-3xl text-purple-400 mb-4">📺</div>
          <h3 class="text-xl font-bold mb-2">Pantalla OLED 144Hz</h3>
          <p class="text-gray-400 text-sm">Brillo pico de 3500 nits con tecnología de fluidez adaptativa de respuesta ultra viva.</p>
        </div>
        <div class="glass p-8 rounded-3xl hover:border-pink-500 transition duration-300 spec-card">
          <div class="text-3xl text-pink-400 mb-4">🔋</div>
          <h3 class="text-xl font-bold mb-2">Carga Holográfica 120W</h3>
          <p class="text-gray-400 text-sm">0 a 100% en tan solo 12 minutos con preservación de salud celular de 10 años.</p>
        </div>
      </div>
    </section>

    <section id="page-camera" class="page w-full text-center">
      <span class="text-purple-400 text-xs font-bold tracking-widest uppercase">Fotografía Biónica</span>
      <h2 class="text-5xl font-black mt-2 mb-8">Sensor 300 MP con Sensor de Fotones</h2>
      <div class="max-w-3xl mx-auto glass p-12 rounded-3xl relative overflow-hidden">
        <div class="w-48 h-48 rounded-full bg-gradient-to-tr from-cyan-500 to-purple-600 mx-auto glow-cyan flex items-center justify-center animate-pulse">
          <span class="text-lg font-bold text-white">PROCESADO AI</span>
        </div>
        <p class="mt-8 text-gray-300">
          La cámara del S27 no solo captura luz, predice la trayectoria de los fotones en entornos de oscuridad total para renderizar imágenes en calidad cinematográfica de manera nativa.
        </p>
      </div>
    </section>

    <section id="page-design" class="page w-full text-center">
      <h2 class="text-4xl font-bold mb-4">Diseño Nano-Titanio</h2>
      <p class="text-gray-400 max-w-md mx-auto mb-8">Estructura unibody ultracompacta diseñada con materiales aeroespaciales.</p>
      <div id="interactive-box" class="w-64 h-64 mx-auto glass rounded-3xl flex items-center justify-center cursor-grab border border-cyan-400/40 glow-cyan">
        <p class="text-sm font-mono text-cyan-300">Arrastra para rotar la estructura</p>
      </div>
    </section>

  </main>

  <script>
    // --- 1. ROUTER MULTI-PÁGINA CON GSAP ---
    function navigateTo(pageId) {
      const activePage = document.querySelector('.page.active');
      const targetPage = document.getElementById(`page-${pageId}`);
      
      if (activePage === targetPage) return;

      // Animación de salida de la página actual
      gsap.to(activePage, {
        opacity: 0,
        y: -20,
        duration: 0.4,
        onComplete: () => {
          activePage.classList.remove('active');
          targetPage.classList.add('active');
          
          // Animación de entrada de la nueva página
          gsap.fromTo(targetPage, 
            { opacity: 0, y: 20 },
            { opacity: 1, y: 0, duration: 0.5 }
          );

          // Animaciones específicas por página
          if(pageId === 'specs') {
            gsap.from('.spec-card', { opacity: 0, y: 30, stagger: 0.15, duration: 0.6 });
          }
        }
      });
    }

    // --- 2. ANIMACIÓN FLUIDA EN MOUSE HOVER (Card 3D Tilt) ---
    const card = document.getElementById('phone-card');
    card.addEventListener('mousemove', (e) => {
      const rect = card.getBoundingClientRect();
      const x = e.clientX - rect.left - rect.width/2;
      const y = e.clientY - rect.top - rect.height/2;
      
      gsap.to(card, {
        rotateY: x / 10,
        rotateX: -y / 10,
        duration: 0.3,
        ease: "power2.out"
      });
    });

    card.addEventListener('mouseleave', () => {
      gsap.to(card, { rotateY: 0, rotateX: 0, duration: 0.5 });
    });

    // --- 3. ANIMACIÓN CANVAS 3D DE FONDO (Three.js) ---
    const canvas = document.getElementById('bg-canvas');
    const scene = new THREE.Scene();
    const camera = new THREE.PerspectiveCamera(75, window.innerWidth / window.innerHeight, 0.1, 1000);
    const renderer = new THREE.WebGLRenderer({ canvas, alpha: true });
    
    renderer.setSize(window.innerWidth, window.innerHeight);
    camera.position.z = 5;

    // Partículas vivas flotantes
    const geometry = new THREE.BufferGeometry();
    const count = 300;
    const positions = new Float32Array(count * 3);

    for(let i = 0; i < count * 3; i++) {
      positions[i] = (Math.random() - 0.5) * 15;
    }

    geometry.setAttribute('position', new THREE.BufferAttribute(positions, 3));
    const material = new THREE.PointsMaterial({
      size: 0.05,
      color: 0x06b6d4,
      transparent: true,
      opacity: 0.6
    });

    const particles = new THREE.Points(geometry, material);
    scene.add(particles);

    // Animación de las partículas
    function animateBG() {
      requestAnimationFrame(animateBG);
      particles.rotation.y += 0.001;
      particles.rotation.x += 0.0005;
      renderer.render(scene, camera);
    }
    animateBG();

    // Redimensionar canvas
    window.addEventListener('resize', () => {
      camera.aspect = window.innerWidth / window.innerHeight;
      camera.updateProjectionMatrix();
      renderer.setSize(window.innerWidth, window.innerHeight);
    });

    // Animar la entrada inicial
    gsap.from("#home-text > *", { opacity: 0, y: 30, duration: 0.8, stagger: 0.2 });
  </script>
</body>
</html>
