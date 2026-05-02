<!DOCTYPE html>
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
    <title>Tamagochi Clicker</title>
    <script src="https://telegram.org/js/telegram-web-app.js?62"></script>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;600;700;800&display=swap" rel="stylesheet">
    <style>
        * { margin: 0; padding: 0; box-sizing: border-box; user-select: none; -webkit-tap-highlight-color: transparent; }
        body { font-family: 'Inter', sans-serif; background: var(--tg-theme-bg-color, #1a1a2e); color: var(--tg-theme-text-color, #fff); overflow-x: hidden; min-height: 100vh; }

        .app { max-width: 450px; margin: 0 auto; padding: 16px; padding-bottom: 100px; }

        /* HEADER */
        .header { display: flex; justify-content: space-between; align-items: center; margin-bottom: 16px; }
        .coins { background: linear-gradient(135deg, #f7971e, #ffd200); color: #1a1a2e; padding: 8px 16px; border-radius: 20px; font-weight: 700; font-size: 16px; display: flex; align-items: center; gap: 6px; }
        .level-badge { background: var(--tg-theme-button-color, #5865f2); color: var(--tg-theme-button-text-color, #fff); padding: 6px 12px; border-radius: 20px; font-weight: 600; font-size: 12px; }

        /* PET DISPLAY */
        .pet-container { text-align: center; margin: 10px 0; position: relative; }
        .pet-sprite { width: 180px; height: 180px; margin: 0 auto; position: relative; cursor: pointer; transition: transform 0.1s; }
        .pet-sprite:active { transform: scale(0.92); }
        .pet-name { font-size: 20px; font-weight: 700; margin-top: 4px; }
        .pet-level-text { font-size: 12px; opacity: 0.7; }

        /* EVOLUTION INDICATOR */
        .evolution { display: flex; justify-content: center; gap: 6px; margin: 8px 0; }
        .evo-dot { width: 24px; height: 24px; border-radius: 50%; border: 2px solid #555; display: flex; align-items: center; justify-content: center; font-size: 12px; opacity: 0.3; }
        .evo-dot.active { opacity: 1; border-color: var(--tg-theme-button-color, #5865f2); background: var(--tg-theme-button-color, #5865f2); }

        /* STATS BARS */
        .stats-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 10px; margin: 16px 0; }
        .stat-bar { background: rgba(255,255,255,0.05); border-radius: 12px; padding: 10px; }
        .stat-label { display: flex; justify-content: space-between; font-size: 12px; margin-bottom: 4px; }
        .stat-track { height: 8px; background: rgba(255,255,255,0.1); border-radius: 10px; overflow: hidden; }
        .stat-fill { height: 100%; border-radius: 10px; transition: width 0.5s ease; }
        .stat-fill.hunger { background: linear-gradient(90deg, #f093fb, #f5576c); }
        .stat-fill.happiness { background: linear-gradient(90deg, #4facfe, #00f2fe); }
        .stat-fill.energy { background: linear-gradient(90deg, #43e97b, #38f9d7); }
        .stat-fill.health { background: linear-gradient(90deg, #fa709a, #fee140); }

        /* CLICK AREA */
        .click-area { 
            background: rgba(255,255,255,0.03); 
            border: 2px dashed rgba(255,255,255,0.1); 
            border-radius: 24px; 
            padding: 30px; 
            text-align: center; 
            cursor: pointer; 
            margin: 12px 0;
            transition: background 0.1s;
            position: relative;
            overflow: hidden;
        }
        .click-area:active { background: rgba(255,255,255,0.08); }
        .click-emoji { font-size: 64px; display: block; margin-bottom: 8px; pointer-events: none; }
        .click-hint { font-size: 14px; opacity: 0.6; }

        /* FLOATING COINS ANIMATION */
        .float-coin {
            position: absolute;
            font-size: 24px;
            font-weight: 700;
            color: #ffd200;
            pointer-events: none;
            animation: floatUp 1s ease-out forwards;
        }
        @keyframes floatUp {
            0% { opacity: 1; transform: translateY(0) scale(1); }
            100% { opacity: 0; transform: translateY(-80px) scale(1.5); }
        }

        /* CRITICAL HIT */
        .critical-flash {
            position: absolute; top: 0; left: 0; right: 0; bottom: 0;
            background: radial-gradient(circle, rgba(255,215,0,0.3), transparent);
            animation: flash 0.4s ease-out;
            pointer-events: none;
        }
        @keyframes flash { 0% { opacity: 1; } 100% { opacity: 0; } }

        /* ACTIONS */
        .actions-grid { display: grid; grid-template-columns: repeat(4, 1fr); gap: 8px; margin: 16px 0; }
        .action-btn {
            background: rgba(255,255,255,0.05);
            border: 1px solid rgba(255,255,255,0.1);
            border-radius: 16px;
            padding: 12px 6px;
            text-align: center;
            cursor: pointer;
            transition: all 0.2s;
            color: var(--tg-theme-text-color, #fff);
            font-family: inherit;
            font-size: 12px;
        }
        .action-btn:active { transform: scale(0.92); background: rgba(255,255,255,0.1); }
        .action-btn .icon { font-size: 24px; display: block; margin-bottom: 4px; }
        .action-btn .cost { font-size: 10px; opacity: 0.6; margin-top: 2px; }

        /* SHOP */
        .shop-grid { display: grid; gap: 10px; margin: 16px 0; }
        .shop-item {
            background: rgba(255,255,255,0.05);
            border-radius: 16px;
            padding: 14px;
            display: flex;
            justify-content: space-between;
            align-items: center;
            cursor: pointer;
            transition: background 0.2s;
        }
        .shop-item:active { background: rgba(255,255,255,0.1); }
        .shop-item-info { display: flex; align-items: center; gap: 12px; }
        .shop-item-icon { font-size: 32px; }
        .shop-item-title { font-weight: 600; font-size: 14px; }
        .shop-item-desc { font-size: 11px; opacity: 0.6; }
        .shop-item-price {
            background: var(--tg-theme-button-color, #5865f2);
            color: var(--tg-theme-button-text-color, #fff);
            padding: 6px 14px;
            border-radius: 20px;
            font-weight: 600;
            font-size: 14px;
            white-space: nowrap;
        }

        /* TABS */
        .tabs { display: flex; gap: 8px; margin: 16px 0; }
        .tab {
            flex: 1; padding: 10px; text-align: center;
            border-radius: 12px; cursor: pointer;
            background: rgba(255,255,255,0.05);
            transition: all 0.2s;
            font-weight: 600;
            color: var(--tg-theme-text-color, #fff);
            font-family: inherit;
            border: none;
            font-size: 14px;
        }
        .tab.active { background: var(--tg-theme-button-color, #5865f2); color: var(--tg-theme-button-text-color, #fff); }

        /* EVOLUTION MODAL */
        .modal-overlay {
            position: fixed; top: 0; left: 0; right: 0; bottom: 0;
            background: rgba(0,0,0,0.7);
            display: flex; align-items: center; justify-content: center;
            z-index: 100;
            animation: fadeIn 0.3s;
        }
        @keyframes fadeIn { from { opacity: 0; } to { opacity: 1; } }
        .modal {
            background: var(--tg-theme-bg-color, #1a1a2e);
            border-radius: 24px; padding: 32px 24px;
            text-align: center; max-width: 320px;
            animation: slideUp 0.3s;
            border: 1px solid rgba(255,255,255,0.1);
        }
        @keyframes slideUp { from { transform: translateY(30px); opacity: 0; } to { transform: translateY(0); opacity: 1; } }
        .modal-emoji { font-size: 80px; margin-bottom: 12px; }
        .modal-title { font-size: 24px; font-weight: 800; margin-bottom: 8px; }
        .modal-desc { font-size: 14px; opacity: 0.7; margin-bottom: 20px; }
        .modal-btn {
            background: var(--tg-theme-button-color, #5865f2);
            color: var(--tg-theme-button-text-color, #fff);
            border: none; padding: 14px 40px;
            border-radius: 16px; font-weight: 700;
            cursor: pointer; font-family: inherit; font-size: 16px;
        }

        /* XP BAR */
        .xp-container { margin: 8px 0; }
        .xp-label { display: flex; justify-content: space-between; font-size: 11px; opacity: 0.6; margin-bottom: 3px; }
        .xp-track { height: 4px; background: rgba(255,255,255,0.1); border-radius: 10px; overflow: hidden; }
        .xp-fill { height: 100%; background: linear-gradient(90deg, #a18cd1, #fbc2eb); border-radius: 10px; transition: width 0.3s; }

        /* OFFLINE BANNER */
        .offline-banner {
            background: linear-gradient(135deg, #667eea, #764ba2);
            border-radius: 16px; padding: 14px; text-align: center;
            margin: 10px 0; font-weight: 600; font-size: 14px;
        }

        /* RESPONSIVE */
        @media (max-width: 400px) {
            .pet-sprite { width: 140px; height: 140px; }
            .click-emoji { font-size: 48px; }
            .action-btn { padding: 8px 4px; font-size: 11px; }
        }
    </style>
</head>
<body>
    <div class="app" id="app"></div>

    <script>
        // ============================================================
        // TELEGRAM INTEGRATION
        // ============================================================
        const tg = window.Telegram?.WebApp;
        if (tg) {
            tg.expand();
            tg.ready();
            tg.enableClosingConfirmation();
        }

        // ============================================================
        // API CLIENT
        // ============================================================
        const API = {
            // Для sendData (когда бот и фронт на одном домене)
            sendToBot: (data) => {
                if (tg) {
                    tg.sendData(JSON.stringify(data));
                }
            },
            // HTTP запросы к своему бэкенду (если нужен отдельный сервер)
            fetch: async (endpoint, data) => {
                try {
                    const initData = tg?.initData || '';
                    const res = await fetch(`/api/${endpoint}`, {
                        method: 'POST',
                        headers: { 'Content-Type': 'application/json', 'X-Telegram-Init-Data': initData },
                        body: JSON.stringify(data)
                    });
                    return await res.json();
                } catch (e) {
                    console.error('API error:', e);
                    return { error: 'connection_error' };
                }
            }
        };

        // ============================================================
        // GAME STATE
        // ============================================================
        const GAME_CONFIG = {
            evolutionNames: { 1: 'Яйцо 🥚', 2: 'Малыш 🐣', 3: 'Подросток 🐥', 4: 'Взрослый 🦅', 5: 'Легенда 🐉' },
            evolutionEmojis: { 1: '🥚', 2: '🐣', 3: '🐥', 4: '🦊', 5: '🐉' },
        };

        let state = {
            user: { coins: 0 },
            pet: {
                name: 'Питомец', level: 1, xp: 0, xp_to_next: 100,
                evolution_stage: 1, hunger: 100, happiness: 100,
                energy: 100, health: 100, total_clicks: 0
            },
            inventory: [],
            offline_coins: 0
        };

        let currentTab = 'game';
        let showEvolution = false;

        // ============================================================
        // SERVER ACTIONS (через sendData)
        // ============================================================
        function serverAction(action, subAction) {
            return new Promise((resolve) => {
                // В реальном Mini App используем HTTP API
                // Здесь для демо — симулируем ответ
                handleGameAction(action, subAction).then(resolve);
            });
        }

        // Симуляция серверной логики (в продакшене всё на сервере)
        async function handleGameAction(action, subAction) {
            switch(action) {
                case 'click': {
                    const isCritical = Math.random() < 0.10;
                    let coins = state.pet.energy > 70 ? 1 : 1;
                    if (isCritical) coins *= 3;
                    const xp = isCritical ? 2 : 1;

                    state.user.coins += coins;
                    state.pet.xp += xp;
                    state.pet.energy = Math.max(10, state.pet.energy - 0.5);
                    state.pet.total_clicks++;

                    // Level up
                    let leveled = false;
                    while (state.pet.xp >= state.pet.xp_to_next) {
                        state.pet.xp -= state.pet.xp_to_next;
                        state.pet.level++;
                        state.pet.xp_to_next = Math.floor(100 * Math.pow(1.5, state.pet.level - 1));
                        leveled = true;

                        // Evolution check
                        const evoLevels = {2: 5, 3: 10, 4: 20, 5: 35};
                        for (const [stage, reqLevel] of Object.entries(evoLevels)) {
                            if (state.pet.level >= reqLevel && state.pet.evolution_stage < parseInt(stage)) {
                                state.pet.evolution_stage = parseInt(stage);
                                showEvolution = true;
                            }
                        }
                    }

                    API.sendToBot({ action: 'click' });
                    render();

                    return { coins_earned: coins, xp_earned: xp, is_critical: isCritical, level_up: leveled, new_level: state.pet.level, new_xp: state.pet.xp, new_xp_to_next: state.pet.xp_to_next };
                }
                case 'pet_action': {
                    const effects = {
                        feed: { hunger: 25, energy: -5, cost: 10 },
                        play: { happiness: 25, energy: -15, cost: 15 },
                        rest: { energy: 30, health: 5, cost: 0 },
                        heal: { health: 30, cost: 50 },
                    };
                    const effect = effects[subAction];
                    if (!effect) return { error: 'unknown' };
                    if (state.user.coins < effect.cost) return { error: 'no_coins', need: effect.cost };

                    state.user.coins -= effect.cost;
                    for (const [stat, delta] of Object.entries(effect)) {
                        if (stat === 'cost') continue;
                        state.pet[stat] = Math.min(100, Math.max(0, (state.pet[stat] || 100) + delta));
                    }

                    API.sendToBot({ action: 'pet_action', sub_action: subAction });
                    render();
                    return { success: true };
                }
                case 'buy_item': {
                    const shop = [
                        { id: 'bonus_feed', name: 'Корм Премиум', icon: '🍖', cost: 200, effect: { hunger: 50 } },
                        { id: 'toy', name: 'Игрушка', icon: '🧸', cost: 300, effect: { happiness: 50 } },
                        { id: 'energy_drink', name: 'Энергетик', icon: '⚡', cost: 250, effect: { energy: 50 } },
                        { id: 'medkit', name: 'Аптечка', icon: '💊', cost: 400, effect: { health: 50 } },
                    ];
                    const item = shop.find(i => i.id === subAction);
                    if (!item) return { error: 'unknown_item' };
                    if (state.user.coins < item.cost) return { error: 'no_coins' };

                    state.user.coins -= item.cost;
                    for (const [stat, delta] of Object.entries(item.effect)) {
                        state.pet[stat] = Math.min(100, Math.max(0, (state.pet[stat] || 100) + delta));
                    }

                    render();
                    return { success: true };
                }
            }
        }

        // ============================================================
        // RENDER
        // ============================================================
        const statNames = {
            hunger: '🍔', happiness: '😊', energy: '🔋', health: '❤️'
        };

        const actionButtons = [
            { id: 'feed', icon: '🍖', label: 'Кормить', cost: 10 },
            { id: 'play', icon: '🎾', label: 'Играть', cost: 15 },
            { id: 'rest', icon: '🛌', label: 'Отдых', cost: 0 },
            { id: 'heal', icon: '💊', label: 'Лечить', cost: 50 },
        ];

        const shopItems = [
            { id: 'bonus_feed', icon: '🍖', name: 'Корм Премиум', desc: '+50 к сытости', cost: 200 },
            { id: 'toy', icon: '🧸', name: 'Игрушка', desc: '+50 к счастью', cost: 300 },
            { id: 'energy_drink', icon: '⚡', name: 'Энергетик', desc: '+50 к энергии', cost: 250 },
            { id: 'medkit', icon: '💊', name: 'Аптечка', desc: '+50 к здоровью', cost: 400 },
        ];

        function render() {
            const app = document.getElementById('app');
            const p = state.pet;
            const evoEmoji = GAME_CONFIG.evolutionEmojis[p.evolution_stage] || '🥚';

            // Offline banner
            let offlineHtml = '';
            if (state.offline_coins > 0) {
                offlineHtml = `<div class="offline-banner">🌟 Пока вас не было: +${state.offline_coins} монет!</div>`;
            }

            // Stats bars
            let statsHtml = '';
            for (const [key, icon] of Object.entries(statNames)) {
                const val = Math.round(p[key] || 100);
                statsHtml += `
                    <div class="stat-bar">
                        <div class="stat-label"><span>${icon} ${key === 'hunger' ? 'Голод' : key === 'happiness' ? 'Счастье' : key === 'energy' ? 'Энергия' : 'Здоровье'}</span><span>${val}</span></div>
                        <div class="stat-track"><div class="stat-fill ${key}" style="width:${val}%"></div></div>
                    </div>
                `;
            }

            // Evolution dots
            let evoHtml = '';
            for (let i = 1; i <= 5; i++) {
                const active = p.evolution_stage >= i ? 'active' : '';
                const emoji = GAME_CONFIG.evolutionEmojis[i] || '?';
                evoHtml += `<div class="evo-dot ${active}">${emoji}</div>`;
            }

            // Action buttons
            let actionsHtml = '';
            for (const btn of actionButtons) {
                actionsHtml += `
                    <div class="action-btn" onclick="doPetAction('${btn.id}')">
                        <span class="icon">${btn.icon}</span>
                        ${btn.label}
                        ${btn.cost > 0 ? `<div class="cost">${btn.cost}💰</div>` : '<div class="cost">Бесплатно</div>'}
                    </div>
                `;
            }

            // Shop items
            let shopHtml = '';
            for (const item of shopItems) {
                shopHtml += `
                    <div class="shop-item" onclick="buyItem('${item.id}')">
                        <div class="shop-item-info">
                            <div class="shop-item-icon">${item.icon}</div>
                            <div>
                                <div class="shop-item-title">${item.name}</div>
                                <div class="shop-item-desc">${item.desc}</div>
                            </div>
                        </div>
                        <div class="shop-item-price">${item.cost}💰</div>
                    </div>
                `;
            }

            // XP bar
            const xpPct = Math.min(100, (p.xp / p.xp_to_next) * 100);

            // Evolution modal
            let modalHtml = '';
            if (showEvolution) {
                const evoName = GAME_CONFIG.evolutionNames[p.evolution_stage] || 'Неизвестно';
                modalHtml = `
                    <div class="modal-overlay" onclick="closeEvolution()">
                        <div class="modal" onclick="event.stopPropagation()">
                            <div class="modal-emoji">${evoEmoji}</div>
                            <div class="modal-title">Эволюция!</div>
                            <div class="modal-desc">Твой питомец достиг стадии<br><strong>${evoName}</strong>!</div>
                            <button class="modal-btn" onclick="closeEvolution()">ВАУ! 🎉</button>
                        </div>
                    </div>
                `;
            }

            // Tab content
            let tabContent = '';
            if (currentTab === 'game') {
                tabContent = `
                    <div class="pet-container">
                        <div class="pet-sprite" onclick="doClick(event)">
                            <div id="clickArea" style="font-size: 160px; line-height: 180px;">${evoEmoji}</div>
                        </div>
                        <div class="pet-name">${p.name}</div>
                        <div class="pet-level-text">Уровень ${p.level}</div>
                        <div class="evolution">${evoHtml}</div>
                        <div class="xp-container">
                            <div class="xp-label"><span>XP</span><span>${p.xp}/${p.xp_to_next}</span></div>
                            <div class="xp-track"><div class="xp-fill" style="width:${xpPct}%"></div></div>
                        </div>
                    </div>

                    <div class="click-area" onclick="doClick(event)">
                        <span class="click-emoji">👆</span>
                        <div class="click-hint">Нажми, чтобы заработать монеты!</div>
                    </div>

                    <div class="stats-grid">${statsHtml}</div>

                    <div style="margin-top:12px; font-size:13px; font-weight:600; opacity:0.7;">🎯 Действия</div>
                    <div class="actions-grid">${actionsHtml}</div>
                `;
            } else {
                tabContent = `
                    <div style="margin-top:12px; font-size:13px; font-weight:600; opacity:0.7;">🛍️ Магазин</div>
                    <div class="shop-grid">${shopHtml}</div>
                `;
            }

            app.innerHTML = `
                ${offlineHtml}
                <div class="header">
                    <div class="coins">💰 ${state.user.coins}</div>
                    <div class="level-badge">LVL ${p.level} • ${evoEmoji}</div>
                </div>

                <div class="tabs">
                    <button class="tab ${currentTab === 'game' ? 'active' : ''}" onclick="switchTab('game')">🎮 Игра</button>
                    <button class="tab ${currentTab === 'shop' ? 'active' : ''}" onclick="switchTab('shop')">🛍️ Магазин</button>
                </div>

                ${tabContent}
                ${modalHtml}
            `;

            // Сбрасываем offline_coins после отображения
            state.offline_coins = 0;
        }

        // ============================================================
        // GAME ACTIONS
        // ============================================================
        async function doClick(event) {
            const result = await handleGameAction('click');
            if (!result) return;

            // Floating coin animation
            const area = event.currentTarget;
            const rect = area.getBoundingClientRect();
            const x = event.clientX - rect.left || rect.width / 2;
            const y = event.clientY - rect.top || rect.height / 2;

            const coin = document.createElement('div');
            coin.className = 'float-coin';
            coin.textContent = result.is_critical ? '🎯 +' + result.coins_earned : '+' + result.coins_earned;
            coin.style.left = x + 'px';
            coin.style.top = y + 'px';
            area.appendChild(coin);
            setTimeout(() => coin.remove(), 1000);

            // Critical flash
            if (result.is_critical) {
                const flash = document.createElement('div');
                flash.className = 'critical-flash';
                area.appendChild(flash);
                setTimeout(() => flash.remove(), 400);

                if (tg) tg.HapticFeedback?.impactOccurred('heavy');
            } else {
                if (tg) tg.HapticFeedback?.impactOccurred('light');
            }

            render();
        }

        async function doPetAction(action) {
            const result = await handleGameAction('pet_action', action);
            if (result?.error === 'no_coins') {
                if (tg) tg.showAlert(`Недостаточно монет! Нужно: ${result.need}`);
                return;
            }
            if (result?.success) {
                if (tg) tg.HapticFeedback?.notificationOccurred('success');
            }
            render();
        }

        async function buyItem(itemId) {
            const result = await handleGameAction('buy_item', itemId);
            if (result?.error === 'no_coins') {
                if (tg) tg.showAlert('Недостаточно монет!');
                return;
            }
            if (result?.success) {
                if (tg) tg.HapticFeedback?.notificationOccurred('success');
            }
            render();
        }

        function switchTab(tab) {
            currentTab = tab;
            render();
        }

        function closeEvolution() {
            showEvolution = false;
            render();
        }

        // ============================================================
        // INIT
        // ============================================================
        // Начальное состояние
        render();

        // Периодическое обновление с сервера (каждые 30 сек)
        setInterval(async () => {
            API.sendToBot({ action: 'get_state' });
        }, 30000);

        // Устанавливаем тему Telegram
        if (tg) {
            document.body.style.setProperty('--tg-theme-bg-color', tg.backgroundColor || '#1a1a2e');
            document.body.style.setProperty('--tg-theme-text-color', tg.textColor || '#ffffff');
            document.body.style.setProperty('--tg-theme-button-color', tg.buttonColor || '#5865f2');
            document.body.style.setProperty('--tg-theme-button-text-color', tg.buttonTextColor || '#ffffff');
        }

        console.log('🐾 Tamagochi Clicker Mini App loaded!');
    </script>
</body>
</html>
