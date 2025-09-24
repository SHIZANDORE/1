<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <title>Campo de Girasoles</title>
  <style>
    body, html {
      margin: 0;
      height: 100%;
      overflow: hidden;
    }
    body {
      /* Fondo dividido */
      background: linear-gradient(to top, 
        #1e7a1e 25%,   
        #2e8b57 35%,   
        #5fb3ff 60%,   
        #4a90e2 100%   
      );
      cursor: pointer;
    }
    canvas {
      position: absolute;
      top: 0;
      left: 0;
    }
    .mensaje {
      position: absolute;
      top: 20px;
      width: 100%;
      text-align: center;
      font-size: 32px;
      font-weight: bold;
      color: white;
      text-shadow: 2px 2px 4px rgba(0,0,0,0.4);
      font-family: "Trebuchet MS", Arial, sans-serif;
      padding: 0 20px;  /* espacio a los lados */
      box-sizing: border-box;
    }
    .submensaje {
      position: absolute;
      top: 70px;  
      width: 80%;             
      max-width: 900px;       
      margin: 0 au
