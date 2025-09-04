<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Past Minds - GitHub README</title>
    <style>
        body {
            background-color: #0d1117;
            color: #c9d1d9;
            font-family: 'Courier New', monospace;
            margin: 0;
            padding: 20px;
            overflow-x: hidden;
        }
        
        .container {
            max-width: 900px;
            margin: 0 auto;
            position: relative;
        }
        
        .glitch {
            position: relative;
            animation: glitch 5s infinite;
        }
        
        @keyframes glitch {
            0% { text-shadow: 0 0 red; }
            95% { text-shadow: 0 0 red; }
            96% { text-shadow: -2px 0 blue; }
            97% { text-shadow: 2px 0 green; }
            98% { text-shadow: -2px 0 blue; }
            99% { text-shadow: 2px 0 green; }
            100% { text-shadow: 0 0 red; }
        }
        
        .cyber-border {
            border: 1px solid #238636;
            padding: 20px;
            margin: 20px 0;
            position: relative;
            overflow: hidden;
        }
        
        .cyber-border::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            height: 2px;
            background: linear-gradient(90deg, #238636, #0d1117, #238636);
            animation: scanline 3s linear infinite;
        }
        
        @keyframes scanline {
            0% { transform: translateX(-100%); }
            100% { transform: translateX(100%); }
        }
        
        .matrix-bg {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            z-index: -1;
            opacity: 0.1;
            pointer-events: none;
        }
        
        .hidden {
            display: none;
        }
        
        .easter-egg {
            cursor: pointer;
            color: #238636;
            position: relative;
        }
        
        .easter-egg:hover::after {
            content: '???';
            position: absolute;
            background: #000;
            padding: 2px 5px;
            border: 1px solid #238636;
            border-radius: 3px;
            font-size: 0.8em;
            bottom: 100%;
            left: 50%;
            transform: translateX(-50%);
            white-space: nowrap;
        }
        
        .status-badge {
            display: inline-block;
            padding: 3px 8px;
            border-radius: 3px;
            font-size: 0.8em;
            margin: 0 5px;
        }
        
        .online {
            background-color: #238636;
            color: white;
        }
        
        .offline {
            background-color: #da3633;
            color: white;
        }
        
        .unknown {
            background-color: #bb8000;
            color: white;
        }
        
        code {
            background-color: #161b22;
            padding: 2px 5px;
            border-radius: 3px;
            border: 1px solid #30363d;
        }
        
        pre {
            background-color: #161b22;
            padding: 15px;
            border-radius: 5px;
            border: 1px solid #30363d;
            overflow-x: auto;
            position: relative;
        }
        
        .copy-btn {
            position: absolute;
            right: 5px;
            top: 5px;
            background: #238636;
            border: none;
            color: white;
            padding: 3px 8px;
            border-radius: 3px;
            cursor: pointer;
            opacity: 0.7;
            transition: opacity 0.3s;
        }
        
        .copy-btn:hover {
            opacity: 1;
        }
        
        .brain-progress {
            height: 20px;
            background-color: #161b22;
            border-radius: 10px;
            margin: 10px 0;
            overflow: hidden;
            position: relative;
        }
        
        .brain-progress-fill {
            height: 100%;
            background: linear-gradient(90deg, #238636, #3fb950);
            width: 0%;
            transition: width 2s;
            border-radius: 10px;
        }
        
        .brain-progress-text {
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            display: flex;
            align-items: center;
            justify-content: center;
            color: white;
            font-weight: bold;
            text-shadow: 0 0 3px black;
        }
        
        .hidden-message {
            color: #238636;
            background-color: #0d1117;
            border: 1px solid #238636;
            padding: 10px;
            margin: 10px 0;
            border-radius: 5px;
            font-family: monospace;
            white-space: pre;
            overflow: hidden;
            height: 0;
            transition: height 0.5s;
        }
        
        .console {
            background-color: #000;
            color: #0f0;
            padding: 15px;
            border-radius: 5px;
            font-family: monospace;
            height: 200px;
            overflow-y: auto;
            margin: 20px 0;
        }
        
        .console-input {
            background-color: #000;
            color: #0f0;
            border: 1px solid #238636;
            padding: 5px;
            font-family: monospace;
            width: calc(100% - 100px);
            margin-right: 10px;
        }
        
        .console-btn {
            background-color: #238636;
            color: white;
            border: none;
            padding: 5px 10px;
            font-family: monospace;
            cursor: pointer;
        }
    </style>
</head>
<body>
    <canvas class="matrix-bg" id="matrixBg"></canvas>
    
    <div class="container">
        <h1 class="glitch">🧠 Past Minds</h1>
        
        <blockquote>
            <p><strong>A mente do passado está nas mãos do futuro. A missão está em suas mãos.</strong></p>
        </blockquote>
        
        <div class="cyber-border">
            <pre><code>class PastMindsGame {
    constructor() {
        this.scientist = "Dr. Cortex Malignus";
        this.agent = "Código: Cerebro";
        this.mission = "Recuperar os cérebros históricos roubados";
        this.status = "Em progresso";
        this.augmentations = ["neural_processor", "ocular_implant", "strength_enhancement"];
        this.brainsToRecover = [
            {name: "Albert Einstein", recovered: false},
            {name: "Leonardo da Vinci", recovered: false},
            {name: "Marie Curie", recovered: false},
            {name: "Nikola Tesla", recovered: false},
            {name: "Alan Turing", recovered: false}
        ];
    }
    
    initiateProtocolDelta() {
        console.log("Protocolo Delta iniciado. Ativando visão cibernética...");
        document.querySelectorAll('.hidden').forEach(el => {
            el.style.display = 'block';
        });
        return "Sistema de aumento ativado";
    }
}</code></pre>
            <button class="copy-btn" onclick="copyCode(this)">Copy</button>
        </div>
        
        <h2>🎮 Sobre a Missão</h2>
        <p>Um cientista psicopata invadiu o Museu de Grandes Mentes e roubou os cérebros preservados das figuras mais influentes da história. O governo recrutou você, <strong>Agente Cerebro</strong> - um soldado altamente modificado com implantes cibernéticos de última geração - para recuperar os artefatos roubados e impedir os planos distorcidos do Dr. Malignus.</p>
        <p><strong>Cuidado:</strong> O Dr. Malignus está usando tecnologia de realidade distorcida para proteger seu laboratório secreto. Suas modificações especiais serão essenciais para superar seus desafios.</p>
        
        <h2>⚡ Características do Agente</h2>
        <ul>
            <li><strong>Sistema Neural Aprimorado:</strong> Processamento de informações em tempo real</li>
            <li><strong>Visão Cibernética:</strong> Detecta padrões ocultos e anomalias dimensionais</li>
            <li><strong>Implantes de Força:</strong> Capacidades sobre-humanas para resolver desafios complexos</li>
            <li><strong>Interface Cérebro-Máquina:</strong> Conexão direta com sistemas computacionais</li>
        </ul>
        
        <h2>🚀 Como Iniciar a Missão</h2>
        <div class="cyber-border">
            <pre><code># Clone o repositório para sua estação de trabalho
git clone https://github.com/seu-usuario/past-minds.git

# Acesse o diretório da missão
cd past-minds

# Instale as dependências necessárias
npm install || yarn install

# Inicie a sequência de inicialização
npm start || yarn start</code></pre>
            <button class="copy-btn" onclick="copyCode(this)">Copy</button>
        </div>
        
        <h2>🧩 Easter Eggs e Segredos</h2>
        <p>O projeto contém vários easter eggs relacionados à temática. Aqui estão algumas dicas para encontrá-los:</p>
        <ol>
            <li><span class="easter-egg" onclick="revealEasterEgg(0)">Console Secrets:</span> Digite <code>help()</code> no console do navegador para ver comandos especiais</li>
            <li><span class="easter-egg" onclick="revealEasterEgg(1)">Código Fonte:</span> Procure por funções com nomes suspeitos como <code>initiateProtocolDelta()</code></li>
            <li><span class="easter-egg" onclick="revealEasterEgg(2)">Arquivos Ocultos:</span> Verifique se há arquivos com extensões incomuns</li>
            <li><span class="easter-egg" onclick="revealEasterEgg(3)">Sequência de Teclas:</span> Tente <code>Ctrl+Alt+Shift+M</code> durante o gameplay</li>
        </ol>
        
        <div class="cyber-border hidden" id="easterEgg0">
            <pre><code>// Exemplo de easter egg no código
function activateCyberVision() {
    if (agent.hasAugmentation('ocular_implant')) {
        console.log('%cVisão Cibernética Ativada. Padrões ocultos detectados!', 
                    'color: #0f0; font-weight: bold;');
        revealHiddenPatterns();
    } else {
        console.log('Aprimoramento necessário: Implante Ocular Nível 2');
    }
}</code></pre>
            <button class="copy-btn" onclick="copyCode(this)">Copy</button>
        </div>
        
        <h2>🧠 Cérebros para Recuperar</h2>
        <div id="brainProgress">
            <div class="brain-progress">
                <div class="brain-progress-fill" id="progressFill"></div>
                <div class="brain-progress-text" id="progressText">0% recuperado</div>
            </div>
            
            <ul>
                <li><input type="checkbox" onchange="updateBrainProgress()"> <strong>Albert Einstein</strong> - Teoria da Relatividade</li>
                <li><input type="checkbox" onchange="updateBrainProgress()"> <strong>Leonardo da Vinci</strong> - Inventor Renascentista</li>
                <li><input type="checkbox" onchange="updateBrainProgress()"> <strong>Marie Curie</strong> - Radioatividade</li>
                <li><input type="checkbox" onchange="updateBrainProgress()"> <strong>Nikola Tesla</strong> - Eletricidade</li>
                <li><input type="checkbox" onchange="updateBrainProgress()"> <strong>Alan Turing</strong> - Ciência da Computação</li>
            </ul>
        </div>
        
        <h2>🛠 Tecnologias Utilizadas</h2>
        <table>
            <tr>
                <th>Tecnologia</th>
                <th>Uso na Missão</th>
            </tr>
            <tr>
                <td>React</td>
                <td>Interface Neural do Agente</td>
            </tr>
            <tr>
                <td>Three.js</td>
                <td>Renderização de Realidade Distorcida</td>
            </tr>
            <tr>
                <td>WebGL</td>
                <td>Processamento Visual Aprimorado</td>
            </tr>
            <tr>
                <td>TensorFlow.js</td>
                <td>Detecção de Padrões Neurais</td>
            </tr>
            <tr>
                <td>Howler.js</td>
                <td>Sistema de Áudio Espacial</td>
            </tr>
        </table>
        
        <h2>🎯 Status da Missão</h2>
        <div class="cyber-border">
            <pre><code>+ Sistema Principal [<span class="status-badge online">ONLINE</span>]
+ Conexão Neural [<span class="status-badge online">ESTÁVEL</span>]
+ Banco de Dados de Cérebros [<span class="status-badge online">SINCRONIZADO</span>]
- Localização do Dr. Malignus [<span class="status-badge unknown">DESCONHECIDA</span>]
! Alerta: Distorções Temporais Detectadas</code></pre>
        </div>
        
        <h2>👥 Equipe de Desenvolvimento</h2>
        <table>
            <tr>
                <th>Papel</th>
                <th>Identificação</th>
            </tr>
            <tr>
                <td>Comandante em Chefe</td>
                <td><code>[REDACTED]</code></td>
            </tr>
            <tr>
                <td>Agente de Inteligência</td>
                <td><code>[DATA EXPUNGED]</code></td>
            </tr>
            <tr>
                <td>Engenheiro Cibernético</td>
                <td><code>[CLASSIFIED]</code></td>
            </tr>
        </table>
        
        <h2>📜 Licença de Missão</h2>
        <p>Este projeto está sob a Licença de Segurança Nível 4. Qualquer tentativa de replicar a tecnologia sem autorização resultará em ação imediata.</p>
        
        <hr>
        
        <p><strong>⚠️ AVISO DE SEGURANÇA:</strong> Esta missão contém elementos de realidade distorcida. Indivíduos com implantes cibernéticos devem consultar seu técnico antes do engajamento prolongado.</p>
        
        <p><strong>Código de Conduta:</strong> Qualquer forma de desrespeito ou assédio não será tolerada e resultará em desconexão imediata da rede neural.</p>
        
        <div style="text-align: center; margin: 30px 0;">
            <h3>A missão aguarda. O tempo é essencial.</h3>
            <button style="background-color: #238636; color: white; border: none; padding: 10px 20px; font-size: 1.2em; cursor: pointer;" onclick="initiateMission()">INICIAR MISSÃO</button>
        </div>
        
        <div class="hidden-message" id="hiddenMessage"></div>
        
        <div class="console" id="console">
            <div>Sistema inicializado. Digite 'help' para ver os comandos disponíveis.</div>
        </div>
        <div>
            <input type="text" class="console-input" id="consoleInput" placeholder=">">
            <button class="console-btn" onclick="processCommand()">Executar</button>
        </div>
        
        <details>
            <summary>🚨 ALERTA DE SEGURANÇA (Nível 5)</summary>
            <br>
            <strong>APENAS PARA OLHOS AUTORIZADOS</strong>
            <p>Se você está lendo esta mensagem, significa que o Dr. Malignus já comprometeu nossos sistemas principais. Use o código de emergência <code>X9-Gamma</code> para ativar os protocolos de contingência.</p>
            <div class="cyber-border">
                <pre><code># Execute em caso de comprometimento do sistema
def emergency_protocol():
    if input("Código de Autorização: ") == "X9-Gamma":
        initiate_lockdown()
        activate_backup_neurals()
        send_distress_signal()
    else:
        self_destruct()</code></pre>
                <button class="copy-btn" onclick="copyCode(this)">Copy</button>
            </div>
            <p><strong>NÃO COMPARTILHE ESTAS INFORMAÇÕES</strong></p>
        </details>
    </div>

    <script>
        // Matrix background effect
        const canvas = document.getElementById('matrixBg');
        const ctx = canvas.getContext('2d');
        
        canvas.width = window.innerWidth;
        canvas.height = window.innerHeight;
        
        const letters = '01010101010101010101010101010101010101010101010101010101010101010101010101010101';
        const fontSize = 14;
        const columns = canvas.width / fontSize;
        
        const drops = [];
        for (let i = 0; i < columns; i++) {
            drops[i] = 1;
        }
        
        function drawMatrix() {
            ctx.fillStyle = 'rgba(13, 17, 23, 0.1)';
            ctx.fillRect(0, 0, canvas.width, canvas.height);
            
            ctx.fillStyle = '#238636';
            ctx.font = `${fontSize}px monospace`;
            
            for (let i = 0; i < drops.length; i++) {
                const text = letters[Math.floor(Math.random() * letters.length)];
                ctx.fillText(text, i * fontSize, drops[i] * fontSize);
                
                if (drops[i] * fontSize > canvas.height && Math.random() > 0.975) {
                    drops[i] = 0;
                }
                
                drops[i]++;
            }
        }
        
        setInterval(drawMatrix, 50);
        
        // Easter egg functionality
        function revealEasterEgg(index) {
            const egg = document.getElementById(`easterEgg${index}`);
            if (egg) {
                egg.classList.toggle('hidden');
            }
        }
        
        // Brain progress functionality
        function updateBrainProgress() {
            const checkboxes = document.querySelectorAll('#brainProgress input[type="checkbox"]');
            const progressFill = document.getElementById('progressFill');
            const progressText = document.getElementById('progressText');
            
            let checked = 0;
            checkboxes.forEach(checkbox => {
                if (checkbox.checked) checked++;
            });
            
            const percentage = (checked / checkboxes.length) * 100;
            progressFill.style.width = `${percentage}%`;
            progressText.textContent = `${percentage}% recuperado`;
            
            if (percentage === 100) {
                progressText.innerHTML = '100% recuperado! <span style="color: #ff0;">Missão Cumprida!</span>';
            }
        }
        
        // Copy code functionality
        function copyCode(button) {
            const codeElement = button.previousElementSibling;
            const textArea = document.createElement('textarea');
            textArea.value = codeElement.textContent;
            document.body.appendChild(textArea);
            textArea.select();
            document.execCommand('copy');
            document.body.removeChild(textArea);
            
            const originalText = button.textContent;
            button.textContent = 'Copied!';
            setTimeout(() => {
                button.textContent = originalText;
            }, 2000);
        }
        
        // Console functionality
        function processCommand() {
            const input = document.getElementById('consoleInput');
            const console = document.getElementById('console');
            const command = input.value.trim();
            input.value = '';
            
            console.innerHTML += `<div>> ${command}</div>`;
            
            switch(command.toLowerCase()) {
                case 'help':
                    console.innerHTML += `<div>Comandos disponíveis: help, status, activate, secret, mission</div>`;
                    break;
                case 'status':
                    console.innerHTML += `<div>Status do sistema: Ótimo</div>`;
                    console.innerHTML += `<div>Implantes ativos: neural_processor, ocular_implant, strength_enhancement</div>`;
                    break;
                case 'activate':
                    console.innerHTML += `<div>Ativando protocolo delta...</div>`;
                    console.innerHTML += `<div>Visão cibernética ativada. Easter eggs revelados!</div>`;
                    document.querySelectorAll('.hidden').forEach(el => {
                        el.style.display = 'block';
                    });
                    break;
                case 'secret':
                    console.innerHTML += `<div>Acessando arquivos secretos...</div>`;
                    console.innerHTML += `<div>Dr. Malignus está escondido no setor 7-G</div>`;
                    break;
                case 'mission':
                    console.innerHTML += `<div>Missão: Recuperar os cérebros roubados</div>`;
                    console.innerHTML += `<div>Progresso: ${document.getElementById('progressText').textContent}</div>`;
                    break;
                default:
                    console.innerHTML += `<div>Comando não reconhecido: ${command}</div>`;
            }
            
            console.scrollTop = console.scrollHeight;
        }
        
        // Initiate mission
        function initiateMission() {
            const message = document.getElementById('hiddenMessage');
            message.style.height = '100px';
            message.textContent = `Iniciando sequência de inicialização...
Ativando implantes cibernéticos...
Conectando à rede neural...
Sistema pronto. Boa sorte, Agente Cerebro.`;
            
            setTimeout(() => {
                document.querySelector('button[onclick="initiateMission()"]').textContent = 'MISSÃO INICIADA';
            }, 3000);
        }
        
        // Keyboard shortcuts
        document.addEventListener('keydown', (e) => {
            if (e.ctrlKey && e.altKey && e.shiftKey && e.key === 'M') {
                alert('Modo de desenvolvedor ativado! Easter eggs revelados.');
                document.querySelectorAll('.hidden').forEach(el => {
                    el.style.display = 'block';
                });
            }
            
            if (e.key === 'Enter' && document.getElementById('consoleInput') === document.activeElement) {
                processCommand();
            }
        });
        
        // Add help function to global scope
        window.help = function() {
            console.log(`%cPast Minds - Comandos do Console`, 'color: #0f0; font-size: 16px; font-weight: bold;');
            console.log(`%c
Comandos disponíveis:
- help(): Mostra esta mensagem
- activateCyberVision(): Ativa a visão cibernética
- initiateProtocolDelta(): Inicia o protocolo delta
- checkMissionStatus(): Verifica o status da missão
            `, 'color: #0f0;');
        };
        
        window.activateCyberVision = function() {
            console.log(`%cVisão Cibernética Ativada!`, 'color: #0f0; font-size: 20px; font-weight: bold;');
            console.log(`%cPadrões ocultos detectados. Easter eggs revelados!`, 'color: #0f0;');
            document.querySelectorAll('.hidden').forEach(el => {
                el.style.display = 'block';
            });
        };
        
        window.initiateProtocolDelta = function() {
            console.log(`%cProtocolo Delta Iniciado!`, 'color: #0f0; font-size: 20px; font-weight: bold;');
            console.log(`%cSistema de aumento ativado. Todos os recursos liberados.`, 'color: #0f0;');
            document.querySelectorAll('input[type="checkbox"]').forEach(checkbox => {
                checkbox.checked = true;
            });
            updateBrainProgress();
        };
        
        window.checkMissionStatus = function() {
            const checkboxes = document.querySelectorAll('#brainProgress input[type="checkbox"]');
            let checked = 0;
            checkboxes.forEach(checkbox => {
                if (checkbox.checked) checked++;
            });
            
            console.log(`%cStatus da Missão: ${checked}/${checkboxes.length} cérebros recuperados`, 'color: #0f0;');
        };
    </script>
</body>
</html>
