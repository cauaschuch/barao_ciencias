<!DOCTYPE html>
<html lang="pt-br">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Folder Interativo - Barão Ciências</title>
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
  <style>
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }

    :root {
      --primary: #045c87;
      --secondary: #0d8bc5;
      --accent: #f39c12;
      --light: #f0f8ff;
      --dark: #333;
      --success: #27ae60;
      --warning: #e74c3c;
    }

    body {
      font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
      background: linear-gradient(135deg, #f0f8ff, #e6f2fa);
      color: var(--dark);
      line-height: 1.6;
      padding: 20px;
      min-height: 100vh;
    }

    .container {
      max-width: 1200px;
      margin: 0 auto;
    }

    header {
      text-align: center;
      padding: 2rem;
      background: linear-gradient(120deg, var(--primary), var(--secondary));
      color: white;
      border-radius: 15px;
      margin-bottom: 2rem;
      box-shadow: 0 8px 16px rgba(0, 0, 0, 0.1);
    }

    header h1 {
      font-size: 2.5rem;
      margin-bottom: 1rem;
      display: flex;
      align-items: center;
      justify-content: center;
      gap: 15px;
    }

    .logo {
      font-size: 3rem;
      color: var(--accent);
    }

    .tagline {
      font-size: 1.2rem;
      max-width: 800px;
      margin: 0 auto;
      opacity: 0.9;
    }

    .grid-container {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
      gap: 25px;
      margin-bottom: 2rem;
    }

    .card {
      background: white;
      border-radius: 15px;
      overflow: hidden;
      box-shadow: 0 6px 12px rgba(0, 0, 0, 0.08);
      transition: transform 0.3s ease, box-shadow 0.3s ease;
    }

    .card:hover {
      transform: translateY(-5px);
      box-shadow: 0 12px 20px rgba(0, 0, 0, 0.12);
    }

    .card-header {
      background: linear-gradient(120deg, var(--secondary), var(--primary));
      color: white;
      padding: 1.2rem;
      display: flex;
      align-items: center;
      gap: 12px;
    }

    .card-header i {
      font-size: 1.8rem;
    }

    .card-body {
      padding: 1.5rem;
    }

    .card h3 {
      margin-bottom: 1rem;
      color: var(--primary);
      border-bottom: 2px solid var(--light);
      padding-bottom: 0.5rem;
    }

    .card ul {
      list-style-type: none;
      padding-left: 0;
    }

    .card li {
      padding: 0.8rem 0;
      border-bottom: 1px dashed #e0e0e0;
      display: flex;
      align-items: flex-start;
      gap: 10px;
    }

    .card li:last-child {
      border-bottom: none;
    }

    .card li i {
      color: var(--success);
      margin-top: 4px;
    }

    .qr-container {
      text-align: center;
      padding: 1.5rem;
      background: #e6f2fa;
      border-radius: 15px;
      margin-top: 1.5rem;
    }

    .qr-container img {
      max-width: 180px;
      display: block;
      margin: 0 auto 1rem;
      border: 8px solid white;
      border-radius: 12px;
    }

    .tutorial {
      background: white;
      border-radius: 15px;
      padding: 2rem;
      margin-bottom: 2rem;
      box-shadow: 0 6px 12px rgba(0, 0, 0, 0.08);
    }

    .tutorial-header {
      text-align: center;
      margin-bottom: 2rem;
      color: var(--primary);
    }

    .tutorial-header h2 {
      font-size: 2rem;
      margin-bottom: 0.5rem;
    }

    .tutorial-steps {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
      gap: 25px;
    }

    .step {
      background: #f9f9f9;
      border-radius: 12px;
      padding: 1.5rem;
      border-left: 4px solid var(--accent);
    }

    .step-number {
      display: inline-block;
      background: var(--accent);
      color: white;
      width: 32px;
      height: 32px;
      border-radius: 50%;
      text-align: center;
      line-height: 32px;
      margin-bottom: 1rem;
      font-weight: bold;
    }

    .step h4 {
      color: var(--primary);
      margin-bottom: 0.8rem;
      font-size: 1.2rem;
    }

    .step-image {
      height: 180px;
      background: linear-gradient(45deg, #e0f7fa, #bbdefb);
      border-radius: 10px;
      margin: 1rem 0;
      display: flex;
      align-items: center;
      justify-content: center;
      color: var(--primary);
      font-weight: bold;
      font-size: 1.1rem;
      text-align: center;
      padding: 20px;
    }

    .tip-box {
      background: #fff8e1;
      border-left: 4px solid var(--accent);
      padding: 1.2rem;
      border-radius: 0 8px 8px 0;
      margin: 1.5rem 0;
    }

    .tip-box i {
      color: var(--accent);
      margin-right: 10px;
    }

    .contact {
      text-align: center;
      padding: 2rem;
      background: linear-gradient(120deg, var(--primary), var(--secondary));
      color: white;
      border-radius: 15px;
      margin-top: 2rem;
    }

    .contact h3 {
      margin-bottom: 1.5rem;
      font-size: 1.8rem;
    }

    .contact-buttons {
      display: flex;
      justify-content: center;
      gap: 20px;
      flex-wrap: wrap;
      margin-top: 1.5rem;
    }

    .contact-btn {
      background: white;
      color: var(--primary);
      padding: 0.8rem 1.5rem;
      border-radius: 50px;
      text-decoration: none;
      font-weight: bold;
      display: flex;
      align-items: center;
      gap: 8px;
      transition: all 0.3s ease;
    }

    .contact-btn:hover {
      transform: scale(1.05);
      box-shadow: 0 4px 10px rgba(0, 0, 0, 0.15);
    }

    footer {
      text-align: center;
      padding: 2rem 0;
      color: var(--primary);
      font-weight: 500;
      margin-top: 2rem;
    }

    @media (max-width: 768px) {
      .grid-container {
        grid-template-columns: 1fr;
      }
      
      .tutorial-steps {
        grid-template-columns: 1fr;
      }
      
      .contact-buttons {
        flex-direction: column;
        align-items: center;
      }
    }
  </style>
</head>
<body>
  <div class="container">
    <header>
      <h1><i class="fas fa-atom logo"></i> Folder Interativo - Barão Ciências</h1>
      <p class="tagline">Seu guia completo para explorar o portal de ciências do Barão</p>
    </header>

    <div class="grid-container">
      <div class="card">
        <div class="card-header">
          <i class="fas fa-door-open"></i>
          <h2>Acesso ao Site</h2>
        </div>
        <div class="card-body">
          <h3>Como acessar?</h3>
          <ul>
            <li><i class="fas fa-check-circle"></i> Abra seu navegador (Chrome, Firefox, Edge)</li>
            <li><i class="fas fa-check-circle"></i> Digite no campo de endereço:</li>
            <li class="highlight">https://cauaschuch.github.io/barao_ciencias/</li>
            <li><i class="fas fa-check-circle"></i> Pressione <code>Enter</code></li>
          </ul>
          
          <div class="qr-container">
            <h3>Acesso rápido via QR Code</h3>
            <img src="https://api.qrserver.com/v1/create-qr-code/?data=https://cauaschuch.github.io/barao_ciencias/&size=200x200" alt="QR Code">
            <p>Use a câmera do seu celular para escanear</p>
          </div>
        </div>
      </div>

      <div class="card">
        <div class="card-header">
          <i class="fas fa-sitemap"></i>
          <h2>Mapa do Site</h2>
        </div>
        <div class="card-body">
          <h3>Navegação Principal</h3>
          <ul>
            <li><i class="fas fa-book"></i> <strong>Disciplinas:</strong> Conteúdos de Física, Química, Biologia, Matemática</li>
            <li><i class="fas fa-download"></i> <strong>Materiais Didáticos:</strong> Listas, resumos e apostilas para download</li>
            <li><i class="fas fa-flask"></i> <strong>Projetos & Eventos:</strong> Feiras, olimpíadas e experiências</li>
            <li><i class="fas fa-video"></i> <strong>Vídeos Educativos:</strong> Demonstrações e aulas em vídeo</li>
            <li><i class="fas fa-images"></i> <strong>Galeria:</strong> Fotos de projetos e eventos</li>
          </ul>
          
          <div class="tip-box">
            <i class="fas fa-lightbulb"></i>
            <strong>Dica:</strong> Use o menu superior para navegar rapidamente entre as seções
          </div>
        </div>
      </div>

      <div class="card">
        <div class="card-header">
          <i class="fas fa-graduation-cap"></i>
          <h2>Recursos Especiais</h2>
        </div>
        <div class="card-body">
          <h3>Funcionalidades Úteis</h3>
          <ul>
            <li><i class="fas fa-search"></i> <strong>Busca Inteligente:</strong> Encontre conteúdos específicos</li>
            <li><i class="fas fa-filter"></i> <strong>Filtros por Disciplina:</strong> Organize por matéria ou tema</li>
            <li><i class="fas fa-bookmark"></i> <strong>Favoritos:</strong> Salve materiais para acesso rápido</li>
            <li><i class="fas fa-bell"></i> <strong>Notificações:</strong> Fique sabendo de novos conteúdos</li>
            <li><i class="fas fa-mobile-alt"></i> <strong>Design Responsivo:</strong> Acesse de qualquer dispositivo</li>
          </ul>
          
          <div class="tip-box">
            <i class="fas fa-lightbulb"></i>
            <strong>Dica:</strong> Use Ctrl+F para buscar palavras-chave em qualquer página
          </div>
        </div>
      </div>
    </div>

    <div class="tutorial">
      <div class="tutorial-header">
        <h2><i class="fas fa-graduation-cap"></i> Tutoriais Passo a Passo</h2>
        <p>Aprenda a usar os principais recursos do site</p>
      </div>
      
      <div class="tutorial-steps">
        <div class="step">
          <div class="step-number">1</div>
          <h4>Como Encontrar Materiais</h4>
          <p>1. Acesse a seção "Disciplinas" no menu superior</p>
          <p>2. Selecione a matéria desejada</p>
          <p>3. Escolha o tópico específico</p>
          <p>4. Clique nos materiais disponíveis</p>
          <div class="step-image">
            <i class="fas fa-book-open fa-3x"></i>
            <p>Imagem ilustrativa da navegação</p>
          </div>
        </div>
        
        <div class="step">
          <div class="step-number">2</div>
          <h4>Como Baixar Arquivos</h4>
          <p>1. Localize o material desejado</p>
          <p>2. Clique no botão de download</p>
          <p>3. Escolha o formato (PDF, DOC)</p>
          <p>4. Salve em seu dispositivo</p>
          <div class="step-image">
            <i class="fas fa-file-download fa-3x"></i>
            <p>Exemplo de botão de download</p>
          </div>
        </div>
        
        <div class="step">
          <div class="step-number">3</div>
          <h4>Como Acompanhar Projetos</h4>
          <p>1. Vá para "Projetos & Eventos"</p>
          <p>2. Selecione o projeto de interesse</p>
          <p>3. Veja fotos, vídeos e descrições</p>
          <p>4. Confira datas e participantes</p>
          <div class="step-image">
            <i class="fas fa-project-diagram fa-3x"></i>
            <p>Visualização de projetos</p>
          </div>
        </div>
      </div>
      
      <div class="tip-box">
        <i class="fas fa-lightbulb"></i>
        <strong>Dica Avançada:</strong> Crie uma conta para salvar seu progresso, favoritar conteúdos e receber notificações de novos materiais.
      </div>
    </div>
    
    <div class="contact">
      <h3><i class="fas fa-question-circle"></i> Precisa de Ajuda?</h3>
      <p>Entre em contato com nossa equipe de suporte</p>
      
      <div class="contact-buttons">
        <a href="mailto:suporte@baraociencias.com" class="contact-btn">
          <i class="fas fa-envelope"></i> E-mail
        </a>
        <a href="#" class="contact-btn">
          <i class="fas fa-comments"></i> Chat Online
        </a>
        <a href="#" class="contact-btn">
          <i class="fas fa-file-alt"></i> FAQ
        </a>
      </div>
    </div>
    
    <footer>
      <p>Folder Educacional &copy; 2023 - Barão Ciências | Atualizado em: Junho/2023</p>
    </footer>
  </div>
</body>
</html>
