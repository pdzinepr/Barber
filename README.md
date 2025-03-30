<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Barber Delacruz - Agende seu Corte</title>
    <link href="https://fonts.googleapis.com/css2?family=Roboto:wght@400;700&family=Oswald:wght@500;700&display=swap" rel="stylesheet">
    <style>
        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
        }

        body {
            font-family: 'Roboto', sans-serif;
            background: linear-gradient(135deg, #0a0a0a, #1c1c1c);
            color: #e0e0e0;
            line-height: 1.6;
            overflow-x: hidden;
            position: relative;
            font-size: 16px; /* Tipografia ajustada */
        }

        /* Fundo animado */
        body::before {
            content: '';
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: radial-gradient(circle, rgba(40, 167, 69, 0.15) 0%, rgba(0, 0, 0, 0) 80%);
            animation: pulse 12s infinite alternate;
            z-index: -1;
        }

        header {
            background: url('https://images.unsplash.com/photo-1595670762239-8031f17f1324?auto=format&fit=crop&w=1920&q=80') no-repeat center/cover;
            color: white;
            padding: 70px 20px;
            text-align: center;
            position: relative;
            box-shadow: inset 0 0 0 1000px rgba(0, 0, 0, 0.3); /* Overlay suave */
            animation: fadeIn 1.2s ease-in;
            border-bottom: 5px solid #28a745;
        }

        header h1 {
            font-family: 'Oswald', sans-serif;
            font-size: 55px;
            font-weight: 700;
            letter-spacing: 3px;
            text-transform: uppercase;
            text-shadow: 1px 1px 4px rgba(40, 167, 69, 0.7); /* Glow discreto */
            animation: glow 2.5s infinite alternate;
        }

        header p {
            font-size: 20px;
            opacity: 0.85;
            margin-top: 10px;
            font-style: italic;
        }

        /* Logo no header */
        header img {
            max-width: 80px;
            position: absolute;
            top: 20px;
            left: 20px;
        }

        .container {
            max-width: 1000px;
            margin: 50px auto;
            padding: 0 20px;
        }

        /* Call-to-Action */
        .cta {
            text-align: center;
            margin: 30px 0;
            color: #28a745;
            font-size: 24px;
            text-shadow: 0 0 8px rgba(40, 167, 69, 0.4);
        }

        section {
            background: rgba(25, 25, 25, 0.9);
            padding: 45px;
            border-radius: 20px;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.5);
            transition: transform 0.3s ease, box-shadow 0.3s ease;
            animation: slideUp 0.6s ease-out;
            border: 2px solid rgba(40, 167, 69, 0.4);
        }

        section:hover {
            transform: translateY(-10px);
            box-shadow: 0 15px 40px rgba(40, 167, 69, 0.5);
        }

        h2 {
            font-family: 'Oswald', sans-serif;
            font-size: 28px; /* Tipografia ajustada */
            color: #28a745;
            margin-bottom: 30px;
            text-align: center;
            text-transform: uppercase;
            letter-spacing: 2px;
            text-shadow: 0 0 8px rgba(40, 167, 69, 0.4);
        }

        /* Texto guia */
        .guide-text {
            text-align: center;
            margin-bottom: 20px;
            color: #e0e0e0;
        }

        /* Input de data com ícone */
        .date-input-wrapper {
            position: relative;
            max-width: 320px;
            margin: 0 auto 25px;
        }

        input[type="date"] {
            padding: 14px;
            font-size: 18px;
            border-radius: 10px;
            border: 2px solid #28a745;
            background-color: #2c2c2c;
            color: #e0e0e0;
            width: 100%;
            display: block;
            transition: all 0.3s ease;
            box-shadow: 0 4px 12px rgba(0, 0, 0, 0.2);
        }

        input[type="date"]:focus {
            border-color: #28a745;
            box-shadow: 0 0 12px rgba(40, 167, 69, 0.6);
            outline: none;
        }

        input[type="date"]::-webkit-calendar-picker-indicator {
            filter: invert(1);
        }

        .date-icon {
            position: absolute;
            top: 50%;
            right: 15px;
            transform: translateY(-50%);
            color: #28a745;
            font-size: 20px;
        }

        button {
            background: linear-gradient(135deg, #28a745, #1e7e34);
            color: white;
            border: none;
            padding: 16px 35px;
            font-size: 18px;
            font-weight: 700;
            cursor: pointer;
            border-radius: 40px;
            transition: all 0.3s ease;
            box-shadow: 0 6px 15px rgba(40, 167, 69, 0.3);
            text-transform: uppercase;
            display: flex;
            align-items: center;
            justify-content: center;
            margin: 0 auto;
        }

        button:hover {
            background: linear-gradient(135deg, #1e7e34, #28a745);
            transform: scale(1.1);
            box-shadow: 0 10px 25px rgba(40, 167, 69, 0.5);
        }

        ul {
            list-style: none;
            padding: 0;
            margin-top: 25px;
        }

        li {
            padding: 18px;
            font-size: 16px; /* Tipografia ajustada */
            display: flex;
            justify-content: space-between;
            align-items: center;
            background: #272727;
            border-radius: 12px;
            margin-bottom: 12px;
            transition: all 0.3s ease;
            animation: slideIn 0.5s ease-out; /* Animação suave */
            box-shadow: 0 4px 10px rgba(0, 0, 0, 0.2);
        }

        li:hover {
            background: #323232;
            transform: translateX(5px); /* Hover suave */
            box-shadow: 0 6px 15px rgba(40, 167, 69, 0.2);
        }

        .indisponivel {
            color: #ff4d4d;
            font-weight: 600;
            text-shadow: 0 0 6px rgba(255, 77, 77, 0.3);
        }

        .disponivel {
            color: #28a745;
            font-weight: 600;
            text-shadow: 0 0 6px rgba(40, 167, 69, 0.3);
        }

        .disponivel button {
            background: linear-gradient(135deg, #28a745, #1e7e34); /* Botões padronizados */
            padding: 8px 15px;
            border-radius: 8px;
            font-size: 16px;
            box-shadow: 0 3px 8px rgba(40, 167, 69, 0.3);
            margin-left: 10px;
        }

        .disponivel button:hover {
            background: linear-gradient(135deg, #1e7e34, #28a745);
            transform: scale(1.05);
        }

        .modal {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0, 0, 0, 0.9);
            justify-content: center;
            align-items: center;
            z-index: 1000;
            animation: fadeIn 0.3s ease-in;
        }

        .modal-content {
            background: #1c1c1c;
            padding: 40px;
            border-radius: 20px;
            text-align: center;
            max-width: 600px;
            width: 90%;
            box-shadow: 0 10px 30px rgba(40, 167, 69, 0.4);
            animation: slideUpModal 0.6s ease-out; /* Animação mais lenta */
            border: 1px solid #28a745;
        }

        .modal-content h2 {
            color: #28a745;
            margin-bottom: 20px;
            font-size: 30px;
            text-shadow: 0 0 8px rgba(40, 167, 69, 0.4);
        }

        .modal-content button {
            margin-top: 25px;
        }

        footer {
            text-align: center;
            padding: 25px;
            background: #141414;
            color: #888;
            position: relative;
            bottom: 0;
            width: 100%;
            border-top: 3px solid #28a745;
            font-size: 15px;
        }

        .social-links a {
            color: #28a745;
            text-decoration: none;
            margin: 0 10px;
        }

        .social-links a:hover {
            text-decoration: underline;
        }

        /* Animações */
        @keyframes fadeIn {
            from { opacity: 0; }
            to { opacity: 1; }
        }

        @keyframes slideUp {
            from { transform: translateY(50px); opacity: 0; }
            to { transform: translateY(0); opacity: 1; }
        }

        @keyframes slideUpModal {
            from { transform: translateY(100px); opacity: 0; }
            to { transform: translateY(0); opacity: 1; }
        }

        @keyframes glow {
            from { text-shadow: 1px 1px 4px rgba(40, 167, 69, 0.7); }
            to { text-shadow: 1px 1px 6px rgba(40, 167, 69, 0.9); }
        }

        @keyframes pulse {
            from { transform: scale(1); opacity: 0.4; }
            to { transform: scale(1.05); opacity: 0.2; }
        }

        @keyframes slideIn {
            from { transform: translateX(-20px); opacity: 0; }
            to { transform: translateX(0); opacity: 1; }
        }

        /* Responsividade */
        @media (max-width: 768px) {
            header h1 {
                font-size: 40px;
            }
            section {
                padding: 20px;
            }
            input[type="date"] {
                max-width: 100%;
            }
            button {
                width: 100%;
                padding: 14px;
            }
            li {
                flex-direction: column;
                align-items: flex-start;
            }
            .disponivel button {
                margin-top: 10px;
                width: 100%;
            }
        }
    </style>
</head>
<body>
    <header>
        <!-- Logo (substitua pelo seu logo) -->
        <img src="logo-tesoura.svg" alt="Logo Barber Delacruz">
        <h1>Barber Delacruz</h1>
        <p>Onde seu estilo ganha vida</p>
    </header>

    <!-- Call-to-Action -->
    <div class="cta">Agende seu corte agora e saia com estilo!</div>

    <div class="container">
        <section id="consultar-horarios">
            <h2>Escolha seu Horário</h2>
            <p class="guide-text">Selecione uma data para ver os horários disponíveis</p>
            <div class="date-input-wrapper">
                <input type="date" id="data-selecionada" aria-label="Selecione uma data">
                <span class="date-icon">📅</span>
            </div>
            <button onclick="consultarHorarios()">Ver Horários <span style="margin-left: 5px;">⏰</span></button>
            <ul id="lista-horarios"></ul>
        </section>
    </div>

    <div id="modal-confirmacao" class="modal">
        <div class="modal-content">
            <span style="font-size: 40px; color: #28a745;">✔️</span>
            <h2>Agendamento Confirmado</h2>
            <p id="mensagem-modal"></p>
            <button onclick="fecharModal()">Entendi</button>
        </div>
    </div>

    <footer>
        <p>© 2025 Barber Delacruz - Feito com sangue, suor e tesoura</p>
        <div class="social-links">
            <a href="#">Instagram</a> | <a href="#">Facebook</a> | <a href="#">Contato</a>
        </div>
    </footer>

    <script>
        const hoje = new Date().toISOString().split('T')[0];
        const inputData = document.getElementById('data-selecionada');
        inputData.setAttribute('min', hoje);

        // Lista de domingos de 2025 pra bloquear
        const domingosBloqueados = [
            "2025-01-05", "2025-01-12", "2025-01-19", "2025-01-26",
            "2025-02-02", "2025-02-09", "2025-02-16", "2025-02-23",
            "2025-03-02", "2025-03-09", "2025-03-16", "2025-03-23", "2025-03-30",
            "2025-04-06", "2025-04-13", "2025-04-20", "2025-04-27",
            "2025-05-04", "2025-05-11", "2025-05-18", "2025-05-25",
            "2025-06-01", "2025-06-08", "2025-06-15", "2025-06-22", "2025-06-29",
            "2025-07-06", "2025-07-13", "2025-07-20", "2025-07-27",
            "2025-08-03", "2025-08-10", "2025-08-17", "2025-08-24", "2025-08-31",
            "2025-09-07", "2025-09-14", "2025-09-21", "2025-09-28",
            "2025-10-05", "2025-10-12", "2025-10-19", "2025-10-26",
            "2025-11-02", "2025-11-09", "2025-11-16", "2025-11-23", "2025-11-30",
            "2025-12-07", "2025-12-14", "2025-12-21", "2025-12-28"
        ];

        // Bloquear apenas os domingos listados
        inputData.addEventListener('input', function () {
            const dataSelecionada = this.value;
            if (domingosBloqueados.includes(dataSelecionada)) {
                this.value = '';
                mostrarModal("Não atendemos nesses dias! Escolha outra data.");
            }
        });

        function consultarHorarios() {
            const lista = document.getElementById('lista-horarios');
            const dataSelecionada = inputData.value;

            if (!dataSelecionada) {
                mostrarModal("Por favor, selecione uma data antes de consultar os horários.");
                return;
            }

            if (domingosBloqueados.includes(dataSelecionada)) {
                lista.innerHTML = '';
                mostrarModal("Não atendemos nesses dias! Escolha outra data.");
                return;
            }

            lista.innerHTML = '';
            let horariosAgendados = JSON.parse(localStorage.getItem(`horarios_${dataSelecionada}`)) || [];

            for (let h = 9; h <= 21; h++) {
                for (let m of ['00', '30']) {
                    if (h === 21 && m === '30') continue;
                    let horario = `${h.toString().padStart(2, '0')}:${m}`;
                    let item = document.createElement('li');
                    
                    if (horariosAgendados.includes(horario)) {
                        item.classList.add('indisponivel');
                        item.textContent = `${horario} - Indisponível`;
                    } else {
                        item.classList.add('disponivel');
                        item.innerHTML = `${horario} - Disponível <button onclick="confirmarAgendamento('${dataSelecionada}', '${horario}')">Agendar</button>`;
                    }
                    lista.appendChild(item);
                }
            }
        }

        function confirmarAgendamento(data, horario) {
            let horariosAgendados = JSON.parse(localStorage.getItem(`horarios_${data}`)) || [];
            if (!horariosAgendados.includes(horario)) {
                horariosAgendados.push(horario);
                localStorage.setItem(`horarios_${data}`, JSON.stringify(horariosAgendados));

                const dataFormatada = new Date(data).toLocaleDateString('pt-BR', { day: '2-digit', month: '2-digit', year: 'numeric' });
                const mensagem = encodeURIComponent(`E aí, quero agendar um corte na Barber Delacruz pra ${dataFormatada} às ${horario}. Confirma aí!`);
                const whatsappLink = `https://wa.me/5544998159910?text=${mensagem}`;
                window.open(whatsappLink, "_blank");

                mostrarModal(`Horário ${horario} agendado pra ${dataFormatada}. Tá confirmado!`);
                consultarHorarios();
            }
        }

        function mostrarModal(mensagem) {
            const modal = document.getElementById('modal-confirmacao');
            const mensagemModal = document.getElementById('mensagem-modal');
            mensagemModal.textContent = mensagem;
            modal.style.display = 'flex';
        }

        function fecharModal() {
            const modal = document.getElementById('modal-confirmacao');
            modal.style.display = 'none';
        }

        window.onload = () => {
            document.querySelector('header').style.opacity = 1;
            document.querySelector('section').style.opacity = 1;
        };
    </script>
</body>
</html>
