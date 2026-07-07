<!DOCTYPE html>
<html lang="bn">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>HAVOC x ZERO-DAY DEFENDERS</title>
    <style>
        /* Global Styles */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Courier New', Courier, monospace;
        }

        body {
            background-color: #050505;
            color: #00ff66;
            overflow-x: hidden;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            min-height: 100vh;
            padding: 20px;
        }

        /* Scanline Effect */
        body::before {
            content: " ";
            display: block;
            position: fixed;
            top: 0; left: 0; bottom: 0; right: 0;
            background: linear-gradient(rgba(18, 16, 16, 0) 50%, rgba(0, 0, 0, 0.25) 50%), linear-gradient(90deg, rgba(255, 0, 0, 0.06), rgba(0, 255, 0, 0.02), rgba(0, 0, 255, 0.06));
            z-index: 2;
            background-size: 100% 2px, 3px 100%;
            pointer-events: none;
        }

        /* Container */
        .container {
            max-width: 800px;
            width: 100%;
            background: rgba(10, 10, 10, 0.9);
            border: 1px solid #00ff66;
            box-shadow: 0 0 20px rgba(0, 255, 102, 0.2);
            padding: 30px;
            border-radius: 5px;
            text-align: center;
        }

        h1 {
            font-size: 2rem;
            text-transform: uppercase;
            letter-spacing: 2px;
            margin-bottom: 10px;
            color: #ff3333;
            text-shadow: 0 0 10px rgba(255, 51, 51, 0.5);
        }

        .subtitle {
            font-size: 1rem;
            color: #888;
            margin-bottom: 30px;
        }

        /* Biometric Scanner Area */
        .scanner-box {
            border: 1px dashed #00ff66;
            padding: 20px;
            display: inline-block;
            margin-bottom: 30px;
            cursor: pointer;
            position: relative;
            background: rgba(0, 255, 102, 0.03);
            transition: all 0.3s ease;
        }

        .scanner-box:hover {
            box-shadow: 0 0 15px rgba(0, 255, 102, 0.4);
        }

        .fingerprint-icon {
            font-size: 60px;
            user-select: none;
        }

        .scan-bar {
            width: 100%;
            height: 4px;
            background-color: #00ff66;
            position: absolute;
            left: 0;
            top: 0;
            box-shadow: 0 0 10px #00ff66;
            animation: scan 2s infinite ease-in-out;
            display: none;
        }

        @keyframes scan {
            0% { top: 0%; }
            50% { top: 100%; }
            100% { top: 0%; }
        }

        /* Console/Terminal */
        .terminal {
            background: #000;
            border: 1px solid #333;
            padding: 15px;
            text-align: left;
            border-radius: 3px;
            height: 200px;
            overflow-y: auto;
            font-size: 0.9rem;
            color: #00ff66;
            margin-bottom: 20px;
        }

        .terminal::-webkit-scrollbar {
            width: 5px;
        }
        .terminal::-webkit-scrollbar-thumb {
            background: #333;
        }

        .log-entry {
            margin-bottom: 5px;
        }
        .log-entry.info { color: #00ff66; }
        .log-entry.warn { color: #ffcc00; }
        .log-entry.danger { color: #ff3333; }

        /* Status Tag */
        .status {
            font-weight: bold;
            color: #ff3333;
            animation: blink 1.5s infinite;
        }

        @keyframes blink {
            0%, 100% { opacity: 1; }
            50% { opacity: 0.3; }
        }

        footer {
            margin-top: 20px;
            font-size: 0.8rem;
            color: #444;
        }
    </style>
</head>
<body>

    <div class="container">
        <h1>HAVOC x ZERO-DAY DEFENDERS</h1>
        <p class="subtitle">THREAT WATCH UNIT // সাধারণ মানুষের সাইবার সুরক্ষায় নিয়োজিত</p>

        <!-- Biometric Login Access -->
        <div class="scanner-box" id="scanner" onclick="startScan()">
            <div class="scan-bar" id="scanBar"></div>
            <div class="fingerprint-icon">🛑</div>
            <p style="margin-top: 10px; font-size: 0.8rem;" id="scanText">ফিঙ্গারপ্রিন্ট দিয়ে Restricted Access আনলক করুন</p>
        </div>

        <!-- Live Terminal Feed -->
        <div class="terminal" id="terminal">
            <div class="log-entry info">[+] System Initializing...</div>
            <div class="log-entry info">[+] Session retention enabled. Monitoring ongoing.</div>
            <div class="log-entry warn">[!] Status: Locked & Monitored.</div>
        </div>

        <p style="font-size: 0.9rem;">
            বর্তমান অবস্থা: <span class="status">RESTRICTED ACCESS</span>
        </p>
    </div>

    <footer>
        &copy; 2026 TANTRA MANTRA BASHIKARAN x HAVOC | Unauthorized access is tracked.
    </footer>

    <script>
        const logs = [
            { type: 'info', text: '[+] Connecting to HAVOC Main Control Panel...' },
            { type: 'info', text: '[+] Security protocols bypassed for Trusted User.' },
            { type: 'warn', text: '[!] Live Threat Scanner: Scanning Bangladesh Region...' },
            { type: 'danger', text: '[ALERT] 2 Fake Cyber Communities detected on radar.' },
            { type: 'info', text: '[+] Invisible Monitoring Active. Target ID logged.' },
            { type: 'danger', text: '[CRITICAL] Zero-Day Attack blocked successfully.' },
            { type: 'info', text: '[+] System Status: Secured. You are not anonymous.' }
        ];

        let logIndex = 0;

        function startScan() {
            const scanBar = document.getElementById('scanBar');
            const scanText = document.getElementById('scanText');
            const terminal = document.getElementById('terminal');

            scanBar.style.display = 'block';
            scanText.innerText = 'বায়োমেট্রিক স্ক্যান করা হচ্ছে... অনুগ্রহ করে অপেক্ষা করুন';
            scanText.style.color = '#ffcc00';

            // Simulate Scan Delay
            setTimeout(() => {
                scanBar.style.style = 'none';
                scanText.innerText = 'ACCESS GRANTED. কন্ট্রোল প্যানেল উন্মুক্ত!';
                scanText.style.color = '#00ff66';
                document.querySelector('.status').innerText = 'SECURE / CONNECTED';
                document.querySelector('.status').style.color = '#00ff66';
                
                // Start filling terminal with logs
                setInterval(addLog, 1500);
            }, 3000);
        }

        function addLog() {
            if (logIndex < logs.length) {
                const terminal = document.getElementById('terminal');
                const entry = document.createElement('div');
                entry.className = `log-entry ${logs[logIndex].type}`;
                entry.innerText = logs[logIndex].text;
                terminal.appendChild(entry);
                terminal.scrollTop = terminal.scrollHeight;
                logIndex++;
            }
        }
    </script>
</body>
</html>
