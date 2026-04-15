<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Unimed Odonto - Orientação para Novos Prestadores</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link href="https://fonts.googleapis.com/css2?family=Montserrat:wght@300;400;600;700&display=swap" rel="stylesheet">
    <style>
        body {
            font-family: 'Montserrat', sans-serif;
            color: #333333;
        }
        .bg-unimed-green { background-color: #00995D; }
        .text-unimed-green { color: #00995D; }
        .bg-unimed-light-green { background-color: #B1D34B; }
        .bg-unimed-bege { background-color: #FFF0C7; }
        .border-unimed-green { border-color: #00995D; }
        
        .btn-primary {
            background-color: #00995D;
            color: white;
            transition: all 0.3s ease;
        }
        .btn-primary:hover {
            background-color: #007d4b;
            transform: translateY(-2px);
        }
        
        .card-step {
            transition: transform 0.3s ease;
        }
        .card-step:hover {
            transform: translateY(-5px);
        }

        /* Spinner for loading state */
        .loader {
            border: 3px solid #f3f3f3;
            border-top: 3px solid #00995D;
            border-radius: 50%;
            width: 20px;
            height: 20px;
            animation: spin 1s linear infinite;
            display: inline-block;
            vertical-align: middle;
        }
        @keyframes spin {
            0% { transform: rotate(0deg); }
            100% { transform: rotate(360deg); }
        }

        html {
            scroll-behavior: smooth;
        }
    </style>
</head>
<body class="bg-white">

    <!-- Header -->
    <header class="sticky top-0 z-50 bg-white shadow-md">
        <div class="container mx-auto px-4 py-4 flex justify-between items-center">
            <div class="flex items-center">
                <div class="bg-unimed-green text-white px-4 py-2 rounded-md font-bold text-xl">
                    Unimed <span class="font-light">Odonto</span>
                </div>
            </div>
            <nav class="hidden md:flex space-x-8 font-medium">
                <a href="#onboarding" class="hover:text-unimed-green transition">Passo a Passo</a>
                <a href="#inteligencia-artificial" class="text-unimed-green font-bold">✨ Inovação</a>
                <a href="#diferenciais" class="hover:text-unimed-green transition">Diferenciais</a>
            </nav>
            <a href="#" class="btn-primary px-6 py-2 rounded-full text-sm font-semibold">
                Portal do Prestador
            </a>
        </div>
    </header>

    <!-- Hero Section -->
    <section class="relative bg-unimed-bege overflow-hidden">
        <div class="container mx-auto px-4 py-16 md:py-24 flex flex-col md:flex-row items-center">
            <div class="md:w-1/2 z-10 text-center md:text-left">
                <h1 class="text-4xl md:text-5xl font-bold text-unimed-green leading-tight mb-6">
                    Bem-vindo à rede Unimed Odonto. <br>
                    <span class="text-black font-light">Vamos transformar sorrisos juntos.</span>
                </h1>
                <p class="text-lg mb-8 text-gray-700 max-w-lg">
                    Seja bem-vindo ao futuro da odontologia. Use nossas ferramentas com IA para agilizar seu credenciamento e atendimento.
                </p>
                <div class="flex flex-col sm:flex-row space-y-4 sm:space-y-0 sm:space-x-4 justify-center md:justify-start">
                    <button class="btn-primary px-8 py-4 rounded-xl font-bold flex items-center justify-center shadow-lg">
                        <svg class="w-5 h-5 mr-2" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 16v1a3 3 0 003 3h10a3 3 0 003-3v-1m-4-4l-4 4m0 0l-4-4m4 4V4"></path></svg>
                        Manual de Boas-Vindas
                    </button>
                    <a href="#inteligencia-artificial" class="bg-white border-2 border-unimed-green text-unimed-green px-8 py-4 rounded-xl font-bold hover:bg-unimed-green hover:text-white transition flex items-center justify-center">
                        Assistente ✨ IA
                    </a>
                </div>
            </div>
            <div class="md:w-1/2 mt-12 md:mt-0 relative">
                <div class="w-full h-80 md:h-96 bg-unimed-light-green rounded-3xl overflow-hidden shadow-2xl flex items-center justify-center text-unimed-green font-bold text-center p-8">
                   
                </div>
            </div>
        </div>
    </section>

    <!-- Gemini AI Section -->
    <section id="inteligencia-artificial" class="py-20 bg-white">
        <div class="container mx-auto px-4">
            <div class="text-center mb-16">
                <span class="bg-unimed-light-green text-unimed-green px-4 py-1 rounded-full text-xs font-bold uppercase tracking-widest">Inovação</span>
                <h2 class="text-3xl font-bold mt-4">Soluções Inteligentes para Prestadores</h2>
                <p class="text-gray-600 mt-2">Tecnologia Gemini para facilitar o seu dia a dia clínico.</p>
            </div>

            <div class="grid grid-cols-1 lg:grid-cols-2 gap-12">
                <!-- Feature 1: Chatbot Assistente -->
                <div class="bg-gray-50 p-8 rounded-3xl border border-gray-100 shadow-sm flex flex-col h-full">
                    <h3 class="text-xl font-bold mb-4 flex items-center">
                        <span class="mr-2">✨</span> Assistente de Credenciamento
                    </h3>
                    <p class="text-sm text-gray-600 mb-6">Tire dúvidas sobre documentação, prazos ou primeiros passos no sistema.</p>
                    
                    <div id="chat-container" class="flex-grow bg-white rounded-xl p-4 mb-4 h-64 overflow-y-auto border border-gray-200 text-sm">
                        <div class="text-gray-400 italic">O assistente está pronto. Como posso ajudar hoje?</div>
                    </div>
                    
                    <div class="flex space-x-2">
                        <input type="text" id="chat-input" placeholder="Ex: Quais documentos para dentista PF?" class="flex-grow px-4 py-3 rounded-xl border border-gray-300 focus:outline-none focus:ring-2 focus:ring-unimed-green">
                        <button onclick="askAssistant()" id="chat-btn" class="btn-primary px-6 py-3 rounded-xl font-bold">Enviar</button>
                    </div>
                </div>

                <!-- Feature 2: Gerador de Justificativa -->
                <div class="bg-gray-50 p-8 rounded-3xl border border-gray-100 shadow-sm flex flex-col h-full">
                    <h3 class="text-xl font-bold mb-4 flex items-center">
                        <span class="mr-2">✨</span> Gerador de Justificativa Técnica
                    </h3>
                    <p class="text-sm text-gray-600 mb-6">Descreva brevemente o caso clínico e geraremos um texto técnico para sua guia de autorização.</p>
                    
                    <textarea id="case-input" rows="4" placeholder="Ex: Paciente com fratura no elemento 11, necessidade de coroa total..." class="w-full px-4 py-3 rounded-xl border border-gray-300 focus:outline-none focus:ring-2 focus:ring-unimed-green mb-4 text-sm"></textarea>
                    
                    <button onclick="generateJustification()" id="gen-btn" class="btn-primary w-full py-4 rounded-xl font-bold mb-4">Gerar Laudo Profissional ✨</button>
                    
                    <div id="justification-output" class="hidden bg-unimed-bege p-4 rounded-xl border border-yellow-200 text-sm text-gray-800 leading-relaxed">
                        <!-- Output will appear here -->
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Onboarding Section -->
    <section id="onboarding" class="py-20 bg-gray-50">
        <div class="container mx-auto px-4">
            <div class="text-center mb-16">
                <h2 class="text-3xl font-bold mb-4">Seu Onboarding em 4 Passos</h2>
                <div class="w-20 h-1 bg-unimed-light-green mx-auto"></div>
            </div>
            
            <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4 gap-8">
                <!-- Step cards (Same as previous version) -->
                <div class="card-step p-8 bg-white rounded-2xl border-t-4 border-unimed-green shadow-sm">
                    <div class="w-12 h-12 bg-unimed-green text-white rounded-full flex items-center justify-center font-bold text-xl mb-6">1</div>
                    <h3 class="text-xl font-bold mb-4 text-unimed-green">Documentação</h3>
                    <p class="text-gray-600 text-sm">Envie as certidões e alvarás necessários através do portal para validação do seu consultório.</p>
                </div>
                <div class="card-step p-8 bg-white rounded-2xl border-t-4 border-unimed-green shadow-sm">
                    <div class="w-12 h-12 bg-unimed-green text-white rounded-full flex items-center justify-center font-bold text-xl mb-6">2</div>
                    <h3 class="text-xl font-bold mb-4 text-unimed-green">Acesso ao Sistema</h3>
                    <p class="text-gray-600 text-sm">Receba suas credenciais e configure seu perfil no sistema GTO para gestão de pacientes.</p>
                </div>
                <div class="card-step p-8 bg-white rounded-2xl border-t-4 border-unimed-green shadow-sm">
                    <div class="w-12 h-12 bg-unimed-green text-white rounded-full flex items-center justify-center font-bold text-xl mb-6">3</div>
                    <h3 class="text-xl font-bold mb-4 text-unimed-green">Autorização</h3>
                    <p class="text-gray-600 text-sm">Entenda o fluxo de aprovação de guias online, garantindo agilidade no atendimento.</p>
                </div>
                <div class="card-step p-8 bg-white rounded-2xl border-t-4 border-unimed-green shadow-sm">
                    <div class="w-12 h-12 bg-unimed-green text-white rounded-full flex items-center justify-center font-bold text-xl mb-6">4</div>
                    <h3 class="text-xl font-bold mb-4 text-unimed-green">Recebimento</h3>
                    <p class="text-gray-600 text-sm">Confira o cronograma de pagamentos e como realizar o faturamento mensal sem erros.</p>
                </div>
            </div>
        </div>
    </section>

    <!-- Footer -->
    <footer class="bg-gray-100 py-12">
        <div class="container mx-auto px-4 text-center">
            <div class="bg-unimed-green text-white px-6 py-2 rounded-md font-bold text-xl inline-block mb-6">
                Unimed <span class="font-light">Odonto</span>
            </div>
            <p class="text-gray-500 text-sm">&copy; 2024 Unimed Odonto. Soluções Inteligentes para Sorrisos Melhores.</p>
        </div>
    </footer>

    <!-- Logic for Gemini API -->
    <script>
        const apiKey = ""; // API Key handled by environment

        async function callGemini(prompt, systemPrompt) {
            const url = `https://generativelanguage.googleapis.com/v1beta/models/gemini-2.5-flash-preview-09-2025:generateContent?key=${apiKey}`;
            
            const payload = {
                contents: [{ parts: [{ text: prompt }] }],
                systemInstruction: { parts: [{ text: systemPrompt }] }
            };

            for (let i = 0; i < 5; i++) {
                try {
                    const response = await fetch(url, {
                        method: 'POST',
                        headers: { 'Content-Type': 'application/json' },
                        body: JSON.stringify(payload)
                    });

                    if (!response.ok) throw new Error('API Error');

                    const result = await response.json();
                    return result.candidates?.[0]?.content?.parts?.[0]?.text || "Desculpe, não consegui processar sua solicitação.";
                } catch (error) {
                    const delay = Math.pow(2, i) * 1000;
                    await new Promise(resolve => setTimeout(resolve, delay));
                }
            }
            return "Erro ao conectar com a Inteligência Artificial após várias tentativas. Por favor, tente novamente mais tarde.";
        }

        async function askAssistant() {
            const input = document.getElementById('chat-input');
            const container = document.getElementById('chat-container');
            const btn = document.getElementById('chat-btn');
            const question = input.value.trim();

            if (!question) return;

            // UI feedback
            input.value = '';
            const userMsg = document.createElement('div');
            userMsg.className = "mb-2 text-right text-unimed-green font-semibold";
            userMsg.innerText = "Você: " + question;
            container.appendChild(userMsg);

            const loadingMsg = document.createElement('div');
            loadingMsg.className = "mb-2 text-gray-500";
            loadingMsg.innerHTML = "✨ Assistente: <span class='loader'></span>";
            container.appendChild(loadingMsg);
            container.scrollTop = container.scrollHeight;

            btn.disabled = true;

            const systemPrompt = "Você é o Assistente Virtual de Credenciamento da Unimed Odonto. Seu objetivo é ajudar novos dentistas (prestadores) com dúvidas sobre o processo de entrada na rede, documentação (PF/PJ), uso do sistema GTO e cronograma de pagamentos. Seja profissional, acolhedor e direto. Use os termos padrão da Unimed Odonto.";
            
            const response = await callGemini(question, systemPrompt);
            
            loadingMsg.innerHTML = "✨ Assistente: " + response;
            container.scrollTop = container.scrollHeight;
            btn.disabled = false;
        }

        async function generateJustification() {
            const input = document.getElementById('case-input');
            const output = document.getElementById('justification-output');
            const btn = document.getElementById('gen-btn');
            const clinicalCase = input.value.trim();

            if (!clinicalCase) return;

            btn.disabled = true;
            btn.innerHTML = "Gerando Laudo... <span class='loader ml-2'></span>";
            output.classList.remove('hidden');
            output.innerHTML = "Analisando caso clínico...";

            const systemPrompt = "Você é um consultor técnico odontológico especialista em auditoria de planos de saúde. Sua tarefa é transformar uma descrição simples de um caso clínico em um laudo técnico profissional e formal em português para ser inserido em guias de autorização. Foque na necessidade clínica do procedimento, critérios de elegibilidade e termos técnicos adequados. O texto deve ser conciso e persuasivo para o auditor.";

            const response = await callGemini(`Transforme este caso em um laudo técnico: ${clinicalCase}`, systemPrompt);

            output.innerHTML = `<strong>Sugestão de Laudo ✨:</strong><br><br>${response.replace(/\n/g, '<br>')}`;
            btn.disabled = false;
            btn.innerHTML = "Gerar Laudo Profissional ✨";
        }
    </script>
</body>
</html>
