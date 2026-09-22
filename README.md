<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Flores Amarillas para Lily</title>
    <style>
      body {
         background-color: #121212;
         color: #ffffff;
         display: flex;
         flex-direction: column;
         align-items: center;
         justify-content: center;
         min-height: 100vh;
         margin: 0;
         font-family: 'Georgia', serif;
         text-align: center;
         overflow: hidden;
      }
      
      .container {
         z-index: 2;
         padding: 30px;
         background: rgba(0, 0, 0, 0.4);
         border-radius: 20px;
         box-shadow: 0 0 20px rgba(255, 215, 0, 0.1);
      }
      
      h1 {
         color: #ffd700;
         font-size: 2.8rem;
         text-shadow: 0 0 15px rgba(255, 215, 0, 0.6);
         margin-bottom: 20px;
         font-weight: normal;
      }
      
      .dedication {
         font-size: 1.6rem;
         font-style: italic;
         color: #ffeb8a;
         margin-top: 30px;
         margin-bottom: 20px;
         letter-spacing: 1px;
      }
      
      .message {
         font-size: 1.2rem;
         line-height: 1.8;
         max-width: 500px;
         margin: 0 auto 30px auto;
         color: #e0e0e0;
      }
      
      .signature {
         font-size: 1.1rem;
         color: #aaaaaa;
         font-style: italic;
      }
      
      /* Animación de la flor central */
      .flower-wrapper {
         position: relative;
         width: 180px;
         height: 180px;
         margin: 20px auto;
         animation: float 4s ease-in-out infinite;
      }
      
      .center {
         position: absolute;
         top: 65px;
         left: 65px;
         width: 50px;
         height: 50px;
         background: radial-gradient(circle, #5c2b0c, #3e1f08);
         border-radius: 50%;
         z-index: 10;
         box-shadow: inset 0 0 10px #1a0a00;
      }
      
      .petal {
         position: absolute;
         width: 40px;
         height: 110px;
         background: linear-gradient(to bottom, #ffeb3b, #ff9800);
         border-radius: 20px 20px 50px 50px;
         top: 0;
         left: 70px;
         transform-origin: 50% 90px;
         z-index: 5;
         box-shadow: 0 0 15px rgba(255, 200, 0, 0.4);
         transition: transform 0.5s ease;
      }
      
      /* Posicionamiento de los pétalos */
      .petal:nth-child(1) { transform: rotate(0deg); }
      .petal:nth-child(2) { transform: rotate(45deg); }
      .petal:nth-child(3) { transform: rotate(90deg); }
      .petal:nth-child(4) { transform: rotate(135deg); }
      .petal:nth-child(5) { transform: rotate(180deg); }
      .petal:nth-child(6) { transform: rotate(225deg); }
      .petal:nth-child(7) { transform: rotate(270deg); }
      .petal:nth-child(8) { transform: rotate(315deg); }

      /* Animación de respiración/flotación */
      @keyframes float {
         0%, 100% { transform: translateY(0) scale(1); }
         50% { transform: translateY(-10px) scale(1.03); }
      }

      /* Contenedor para la lluvia de pétalos */
      .bg-petals {
         position: absolute;
         top: 0; left: 0; width: 100%; height: 100%;
         pointer-events: none;
         z-index: 1;
      }
    </style>
</head>
<body>
    <div class="bg-petals" id="petals"></div>
    
    <div class="container">
        <h1>Para Lily</h1>
        
        <div class="flower-wrapper">
            <div class="petal"></div>
            <div class="petal"></div>
            <div class="petal"></div>
            <div class="petal"></div>
            <div class="petal"></div>
            <div class="petal"></div>
            <div class="petal"></div>
            <div class="petal"></div>
            <div class="center"></div>
        </div>

        <p class="dedication">Gracias por estar siempre, en las buenas y en las malas.</p>
        
        <p class="message">
            Hoy estas flores amarillas son para agradecerte por tu amistad incondicional. Quería regalarte este detalle digital para que sepas lo mucho que valoro que siempre estés ahí para mí.
        </p>
        
        <p class="signature">Con mucho cariño, Nahuel.</p>
    </div>

    <script>
        const petalsContainer = document.getElementById('petals');
        
        function createPetal() {
            const petal = document.createElement('div');
            
            petal.style.position = 'absolute';
            petal.style.width = '12px';
            petal.style.height = '20px';
            petal.style.background = 'rgba(255, 200, 0, 0.7)';
            petal.style.borderRadius = '50% 50% 0 50%';
            petal.style.left = Math.random() * 100 + 'vw';
            petal.style.top = '-30px';
            petal.style.filter = 'blur(1px)';
            petal.style.transform = `rotate(${Math.random() * 360}deg)`;
            
            const duration = Math.random() * 4 + 4; 
            petal.style.transition = `top ${duration}s linear, left ${duration}s ease-in-out`;
            
            petalsContainer.appendChild(petal);

            setTimeout(() => {
                petal.style.top = '110vh';
                petal.style.left = `calc(${petal.style.left} + ${Math.random() * 80 - 40}px)`;
            }, 50);

            setTimeout(() => {
                petal.remove();
            }, duration * 1000);
        }

        setInterval(createPetal, 600);
    </script>
</body>
</html>
