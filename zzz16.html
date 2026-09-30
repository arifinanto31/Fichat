<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no, viewport-fit=cover">
    <title>Fi chat</title>
    <link href="https://fonts.googleapis.com/css2?family=Roboto:wght@400;500;700&display=swap" rel="stylesheet">
    <script src="https://unpkg.com/peerjs@1.5.2/dist/peerjs.min.js"></script>
    <style>
        * { box-sizing: border-box; margin: 0; padding: 0; font-family: 'Roboto', sans-serif; -webkit-tap-highlight-color: transparent; }
        
        html, body { width: 100%; height: 100%; overflow: hidden; background-color: #efeae2; }
        
        #auth-screen {
            position: fixed; top: 0; left: 0; width: 100%; height: 100%;
            background: #f0f2f5; z-index: 9999; display: flex; justify-content: center; align-items: center; padding: 20px;
        }
        .auth-card {
            background: #ffffff; width: 100%; max-width: 400px; padding: 24px; border-radius: 16px; box-shadow: 0 4px 12px rgba(0,0,0,0.1); text-align: center;
        }
        .auth-card h2 { color: #00a884; margin-bottom: 8px; font-size: 1.4rem; }
        .auth-card p { color: #666; font-size: 0.85rem; margin-bottom: 20px; line-height: 1.4; }

        .app-container { width: 100vw; height: 100dvh; display: flex; flex-direction: column; position: relative; background-color: #efeae2; }

        .header {
            background-color: #00a884; color: white; padding: calc(10px + env(safe-area-inset-top)) 16px 10px 16px;
            display: flex; justify-content: space-between; align-items: center; box-shadow: 0 1px 3px rgba(0,0,0,0.15); z-index: 10; flex-shrink: 0;
        }
        .header-profile-info { display: flex; align-items: center; gap: 10px; }
        .header-avatar { width: 36px; height: 36px; border-radius: 50%; object-fit: cover; background: #ddd; }
        .header-title { font-size: 1.05rem; font-weight: 500; }
        .header-status { font-size: 0.75rem; color: #e9edef; }
        .header-actions { display: flex; gap: 8px; }

        .btn-call {
            background: rgba(255, 255, 255, 0.2); border: none; color: white; padding: 6px 10px; border-radius: 6px; font-size: 0.85rem; cursor: pointer; display: flex; align-items: center; justify-content: center;
        }
        .btn-call:disabled { opacity: 0.4; cursor: not-allowed; }

        .tab-content { display: none; flex: 1; flex-direction: column; overflow: hidden; position: relative; }
        .tab-content.active { display: flex; }

        .call-container { display: none; flex-direction: column; background: #111827; position: relative; width: 100%; height: 240px; flex-shrink: 0; border-bottom: 2px solid #374151; }
        .call-container.active { display: flex; }

        .video-grid { display: flex; width: 100%; height: 100%; position: relative; background: #000; }
        video { object-fit: cover; background: #222; }
        #remote-video { width: 100%; height: 100%; }
        #local-video { position: absolute; top: 10px; right: 10px; width: 80px; height: 105px; border-radius: 8px; border: 2px solid #fff; z-index: 2; background: #111; }

        .call-controls {
            position: absolute; bottom: 10px; left: 50%; transform: translateX(-50%); display: flex; gap: 8px; z-index: 3; background: rgba(0,0,0,0.6); padding: 6px 12px; border-radius: 20px;
        }
        .btn-ctrl { background: #ffffff22; border: none; color: white; padding: 6px 12px; border-radius: 14px; font-size: 0.75rem; cursor: pointer; }
        .btn-end { background: #ef4444; }

        .connect-panel { padding: 0; background: #ffffff; height: 100%; overflow-y: auto; }
        .card-box { background: #ffffff; border-radius: 12px; padding: 16px; margin-bottom: 12px; box-shadow: 0 1px 3px rgba(0,0,0,0.05); }
        .card-title { font-size: 0.8rem; font-weight: 700; color: #00a884; margin-bottom: 10px; text-transform: uppercase; }

        input[type="text"], input[type="email"], input[type="password"] {
            width: 100%; padding: 12px; border: 1px solid #d1d5db; border-radius: 8px; font-size: 0.95rem; outline: none; margin-bottom: 10px; background: #fff;
        }
        input:focus { border-color: #00a884; }

        .btn { width: 100%; background-color: #00a884; color: white; border: none; padding: 12px; border-radius: 8px; font-weight: 600; font-size: 0.9rem; cursor: pointer; box-shadow: 0 2px 4px rgba(0, 168, 132, 0.3); }
        .btn:active { background-color: #01755d; }
        .btn-secondary { background-color: #64748b; margin-top: 8px; }

        .id-display-box { background: #f0fdf4; border: 2px dashed #00a884; padding: 12px; border-radius: 8px; text-align: center; margin-bottom: 12px; }
        .id-display-box span { font-size: 0.75rem; color: #64748b; display: block; }
        .id-display-box h3 { font-size: 1.4rem; color: #00a884; letter-spacing: 2px; margin-top: 4px; font-family: monospace; }

        .profile-edit-section { text-align: center; margin-bottom: 15px; }
        .profile-avatar-preview { width: 70px; height: 70px; border-radius: 50%; object-fit: cover; border: 2px solid #00a884; margin: 0 auto 8px auto; display: block; background: #eee; }

        /* Multi-Chat Styles */
        .chat-list-view { flex: 1; overflow-y: auto; background: #fff; display: flex; flex-direction: column; }
        .chat-top-action { padding: 12px 16px; background: #f8fafc; border-bottom: 1px solid #e2e8f0; display: flex; justify-content: space-between; align-items: center; }
        .btn-add-chat { background: #00a884; color: white; border: none; padding: 6px 12px; border-radius: 6px; font-size: 0.8rem; cursor: pointer; font-weight: 500; }
        
        .chat-room-item { display: flex; align-items: center; gap: 12px; padding: 12px 16px; border-bottom: 1px solid #f0f2f5; cursor: pointer; }
        .chat-room-item:hover { background: #f8fafc; }
        .chat-room-avatar { width: 48px; height: 48px; border-radius: 50%; background: #00a884; color: white; display: flex; align-items: center; justify-content: center; font-weight: bold; font-size: 1.1rem; }

        .chat-room-view { display: none; flex: 1; flex-direction: column; height: 100%; }
        .chat-room-view.active { display: flex; }
        .chat-room-header { background: #00a884; color: white; padding: 10px 16px; display: flex; align-items: center; gap: 10px; }
        .back-btn { background: none; border: none; color: white; font-size: 1.2rem; cursor: pointer; }

        .chat-area { flex: 1; padding: 12px; overflow-y: auto; display: flex; flex-direction: column; gap: 10px; background-color: #efeae2; background-image: radial-gradient(#d1ccc0 0.75px, transparent 0.75px); background-size: 15px 15px; }

        .msg-row { display: flex; align-items: flex-end; gap: 6px; max-width: 85%; }
        .msg-row.row-in { align-self: flex-start; }
        .msg-row.row-out { align-self: flex-end; flex-direction: row-reverse; }

        .bubble { padding: 8px 12px; border-radius: 7.5px; font-size: 0.92rem; line-height: 1.35; word-wrap: break-word; box-shadow: 0 1px 0.5px rgba(0,0,0,0.13); }
        .bubble-in { background-color: #ffffff; color: #111b21; border-top-left-radius: 0; }
        .bubble-out { background-color: #d9fdd3; color: #111b21; border-top-right-radius: 0; }
        .bubble img { max-width: 200px; border-radius: 6px; display: block; margin-bottom: 4px; }
        .file-attachment { display: flex; align-items: center; gap: 8px; background: rgba(0,0,0,0.05); padding: 8px; border-radius: 6px; text-decoration: none; color: inherit; font-size: 0.85rem; }

        .input-bar { background-color: #f0f2f5; padding: 8px 10px; display: flex; align-items: center; gap: 8px; border-top: 1px solid #e2e8f0; }
        .input-bar input[type="text"] { flex: 1; padding: 10px 14px; border: none; border-radius: 20px; outline: none; font-size: 0.95rem; background: #ffffff; margin-bottom: 0; }
        .btn-attach { background: transparent; border: none; color: #54656f; font-size: 1.2rem; cursor: pointer; padding: 4px; }
        .btn-send { background-color: #00a884; color: white; border: none; width: 40px; height: 40px; border-radius: 50%; display: flex; justify-content: center; align-items: center; cursor: pointer; flex-shrink: 0; }

        /* TAMPILAN STATUS ALA WHATSAPP */
        .wa-status-section-title { font-size: 0.75rem; font-weight: bold; color: #666; padding: 12px 16px 4px 16px; background: #f0f2f5; text-transform: uppercase; }
        .wa-status-item { display: flex; align-items: center; gap: 14px; padding: 10px 16px; background: white; cursor: pointer; border-bottom: 1px solid #f8fafc; }
        .wa-status-item:hover { background: #f8fafc; }
        
        .wa-status-ring { width: 54px; height: 54px; border-radius: 50%; padding: 2px; display: flex; align-items: center; justify-content: center; position: relative; }
        .wa-status-ring.has-status { border: 2px solid #00a884; }
        .wa-status-ring.no-status { border: 2px dashed #cbd5e1; }
        .wa-status-avatar { width: 100%; height: 100%; border-radius: 50%; object-fit: cover; background: #ddd; }
        
        .wa-status-add-badge {
            position: absolute; bottom: 0; right: 0; width: 18px; height: 18px; background: #00a884; color: white;
            border-radius: 50%; font-size: 12px; display: flex; align-items: center; justify-content: center; border: 2px solid white; font-weight: bold;
        }

        /* Fullscreen Status Story Viewer */
        #status-viewer-modal {
            position: fixed; top: 0; left: 0; width: 100%; height: 100%; background: #000; z-index: 99999; display: none; flex-direction: column; justify-content: space-between; color: white; padding: 10px 0;
        }
        .story-progress-bar-container { display: flex; gap: 4px; padding: 0 10px; width: 100%; }
        .story-progress-segment { flex: 1; height: 3px; background: rgba(255,255,255,0.4); border-radius: 2px; overflow: hidden; }
        .story-progress-fill { width: 0%; height: 100%; background: white; transition: width linear; }
        
        .story-viewer-header { display: flex; align-items: center; gap: 10px; padding: 10px 16px; }
        .story-viewer-avatar { width: 36px; height: 36px; border-radius: 50%; object-fit: cover; background: #555; }
        
        .story-content-box { flex: 1; display: flex; align-items: center; justify-content: center; position: relative; overflow: hidden; text-align: center; padding: 20px; }
        .story-text-display { font-size: 1.3rem; font-weight: 500; word-break: break-word; line-height: 1.4; }
        .story-image-display { max-width: 100%; max-height: 100%; object-fit: contain; border-radius: 8px; }

        .story-footer-action { padding: 10px 16px; display: flex; flex-direction: column; gap: 8px; background: rgba(0,0,0,0.6); }

        .bottom-nav {
            display: flex; background-color: #ffffff; border-top: 1px solid #e2e8f0; height: calc(56px + env(safe-area-inset-bottom)); padding-bottom: env(safe-area-inset-bottom); flex-shrink: 0; z-index: 10;
        }
        .nav-item { flex: 1; display: flex; flex-direction: column; justify-content: center; align-items: center; color: #8e8e93; cursor: pointer; gap: 2px; }
        .nav-item.active { color: #00a884; }
        .nav-label { font-size: 0.7rem; font-weight: 500; }

        .friend-card { display: flex; justify-content: space-between; align-items: center; padding: 10px 12px; background: #fff; border: 1px solid #e2e8f0; border-radius: 8px; margin-bottom: 8px; }
        .friend-info strong { display: block; font-size: 0.9rem; color: #1e293b; }
        .friend-info small { font-size: 0.75rem; color: #64748b; word-break: break-all; font-family: monospace; }
        .friend-actions { display: flex; gap: 6px; flex-shrink: 0; }
        .btn-sm { padding: 6px 10px; font-size: 0.75rem; border-radius: 6px; border: none; cursor: pointer; color: white; background: #00a884; }
        .btn-sm-danger { background: #ef4444; }
    </style>
</head>
<body>

    <!-- LAYAR AUTENTIKASI EMAIL -->
    <div id="auth-screen">
        <div class="auth-card">
            <h2 id="auth-title">Masuk ke Fi chat</h2>
            <p id="auth-desc">Gunakan email dan password Anda untuk verifikasi akun.</p>
            
            <input type="email" id="email-input" placeholder="Namaemail@gmail.com">
            <input type="password" id="password-input" placeholder="Password (min 6 karakter)">
            
            <button class="btn" id="auth-main-btn" onclick="handleAuth()">Masuk</button>
            <button class="btn btn-secondary" id="auth-switch-btn" onclick="toggleAuthMode()">Belum punya akun? Daftar</button>
        </div>
    </div>

    <!-- FULLSCREEN STATUS VIEWER (Gaya WA Story) -->
    <div id="status-viewer-modal">
        <div class="story-progress-bar-container" id="story-progress-container"></div>
        <div class="story-viewer-header">
            <img id="viewer-author-avatar" class="story-viewer-avatar" src="">
            <div>
                <strong id="viewer-author-name">Nama</strong><br>
                <span id="viewer-time" style="font-size:0.7rem; color:#aaa;">Waktu</span>
            </div>
            <button onclick="closeStatusViewer()" style="margin-left:auto; background:none; border:none; color:white; font-size:1.5rem; cursor:pointer;">✕</button>
        </div>
        <div class="story-content-box" id="story-content-box"></div>
        <div class="story-footer-action">
            <div style="display:flex; justify-content:space-between; align-items:center;">
                <button id="viewer-like-btn" onclick="likeActiveStory()" style="background:none; border:none; color:white; font-size:0.9rem; cursor:pointer;">❤️ Suka (0)</button>
            </div>
            <div style="display:flex; gap:6px;">
                <input type="text" id="viewer-comment-input" placeholder="Balas ke chat utama..." style="margin-bottom:0; background:white; color:black; font-size:0.85rem; padding:8px;">
                <button class="btn-sm" onclick="replyStatusToMainChat()">Kirim</button>
            </div>
        </div>
    </div>

    <!-- APLIKASI UTAMA -->
    <div class="app-container">
        <div class="header">
            <div class="header-profile-info">
                <img id="header-avatar-img" src="" class="header-avatar" style="display:none;">
                <div>
                    <div class="header-title" id="header-peer-title">Fi chat</div>
                    <div class="header-status" id="header-status">Menghubungkan...</div>
                </div>
            </div>
            <div class="header-actions">
                <button class="btn-call" id="btn-voice-call" onclick="startCall(false)" disabled>📞</button>
                <button class="btn-call" id="btn-video-call" onclick="startCall(true)" disabled>📹</button>
            </div>
        </div>

        <!-- TAB 1: CHAT -->
        <div id="tab-chat" class="tab-content active">
            <div id="chat-list-view" class="chat-list-view">
                <div class="chat-top-action">
                    <span style="font-size: 0.8rem; font-weight: bold; color: #64748b;">DAFTAR PERCAKAPAN</span>
                    <button class="btn-add-chat" onclick="goToFriendsTab()">+ Tambah Chat</button>
                </div>
                <div id="chat-rooms-container" style="flex:1; overflow-y:auto;"></div>
            </div>

            <div id="chat-room-view" class="chat-room-view">
                <div class="chat-room-header">
                    <button class="back-btn" onclick="closeChatRoom()">←</button>
                    <strong id="active-chat-name">Teman</strong>
                </div>
                <div class="call-container" id="call-box">
                    <div class="video-grid">
                        <video id="remote-video" autoplay playsinline></video>
                        <video id="local-video" autoplay playsinline muted></video>
                    </div>
                    <div class="call-controls">
                        <button class="btn-ctrl" id="btn-toggle-mic" onclick="toggleAudio()">Mute</button>
                        <button class="btn-ctrl" id="btn-toggle-cam" onclick="toggleVideo()">Cam Off</button>
                        <button class="btn-ctrl btn-end" onclick="endCall()">Tutup</button>
                    </div>
                </div>
                <div class="chat-area" id="active-chat-box"></div>
                <div class="input-bar">
                    <input type="file" id="file-input" style="display: none;" onchange="handleFileSelect(event)">
                    <button class="btn-attach" onclick="document.getElementById('file-input').click()" title="Kirim File">📎</button>
                    <input type="text" id="chat-input" placeholder="Ketik pesan..." onkeypress="handleKeyPress(event)">
                    <button class="btn-send" onclick="sendMessage()">➔</button>
                </div>
            </div>
        </div>

        <!-- TAB 2: KONTAK -->
        <div id="tab-friends" class="tab-content">
            <div class="connect-panel" style="padding: 16px;">
                <div class="card-box">
                    <div class="card-title">Tambah ID Teman Baru</div>
                    <input type="text" id="manual-peer-input" placeholder="Masukkan ID Unik Teman...">
                    <button class="btn" onclick="addNewFriendId()">Simpan & Hubungkan</button>
                </div>
                <div class="card-box">
                    <div class="card-title">Daftar Kontak Teman</div>
                    <div id="friends-list-container"></div>
                </div>
            </div>
        </div>

        <!-- TAB 3: STATUS -->
        <div id="tab-status" class="tab-content">
            <div class="connect-panel">
                <div class="wa-status-item" onclick="handleMyStatusClick()">
                    <div class="wa-status-ring" id="my-status-ring-container">
                        <img id="my-status-avatar" class="wa-status-avatar" src="">
                        <div class="wa-status-add-badge" id="my-status-badge">+</div>
                    </div>
                    <div>
                        <strong style="color:#111b21;">Status Saya</strong><br>
                        <span id="my-status-subtitle" style="font-size:0.8rem; color:#667781;">Ketuk untuk memperbarui status</span>
                    </div>
                </div>
                <input type="file" id="status-media-input" accept="image/*" style="display:none;" onchange="postMediaStatus(event)">

                <div class="wa-status-section-title">Pembaruan Terkini</div>
                <div id="wa-status-list-container"></div>
            </div>
        </div>

        <!-- TAB 4: PENGATURAN -->
        <div id="tab-settings" class="tab-content">
            <div class="connect-panel" style="padding: 16px;">
                <div class="card-box profile-edit-section">
                    <img id="profile-preview" src="" class="profile-avatar-preview">
                    <input type="file" id="avatar-file-input" accept="image/*" style="display:none;" onchange="handleAvatarSelect(event)">
                    <button class="btn btn-secondary" style="padding: 6px 12px; font-size: 0.8rem; margin-bottom: 10px;" onclick="document.getElementById('avatar-file-input').click()">Ganti Foto Profil</button>
                    
                    <input type="text" id="profile-name-input" placeholder="Nama Pengguna" style="text-align: center; font-weight: bold;">
                    <button class="btn" style="padding: 8px;" onclick="saveProfileName()">Simpan Nama</button>
                </div>

                <div class="id-display-box">
                    <span>ID UNIK AKUN ANDA (Bagikan ke teman)</span>
                    <h3 id="my-active-pin">---</h3>
                </div>

                <div class="card-box">
                    <button class="btn" style="background-color: #ef4444;" onclick="logout()">Keluar Akun</button>
                </div>
            </div>
        </div>

        <!-- BOTTOM NAVIGATION -->
        <div class="bottom-nav">
            <div id="nav-item-chat" class="nav-item active" onclick="switchTab('tab-chat', this)"><span>💬</span><span class="nav-label">Chat</span></div>
            <div id="nav-item-friends" class="nav-item" onclick="switchTab('tab-friends', this)"><span>👥</span><span class="nav-label">Kontak</span></div>
            <div class="nav-item" onclick="switchTab('tab-status', this)"><span>🔄</span><span class="nav-label">Status</span></div>
            <div class="nav-item" onclick="switchTab('tab-settings', this)"><span>⚙️</span><span class="nav-label">Pengaturan</span></div>
        </div>
    </div>

    <!-- Firebase SDK -->
    <script type="module">
        import { initializeApp } from "https://www.gstatic.com/firebasejs/10.8.0/firebase-app.js";
        import { getAuth, createUserWithEmailAndPassword, signInWithEmailAndPassword, onAuthStateChanged, signOut } from "https://www.gstatic.com/firebasejs/10.8.0/firebase-auth.js";

        const firebaseConfig = {
            apiKey: "AIzaSyBgAULTyWiqJHE808OHtpCmmxf5lfvjF5g",
            authDomain: "fi-chat-cffdc.firebaseapp.com",
            projectId: "fi-chat-cffdc",
            storageBucket: "fi-chat-cffdc.firebasestorage.app",
            messagingSenderId: "279898113095",
            appId: "1:279898113095:web:d1f84a0473771b8fd6dd62"
        };

        const app = initializeApp(firebaseConfig);
        const auth = getAuth(app);

        let isRegisterMode = false;

        window.toggleAuthMode = function() {
            isRegisterMode = !isRegisterMode;
            document.getElementById('auth-title').innerText = isRegisterMode ? "Daftar Akun Baru" : "Masuk ke Fi chat";
            document.getElementById('auth-desc').innerText = isRegisterMode ? "Buat akun menggunakan email & password." : "Gunakan email dan password Anda.";
            document.getElementById('auth-main-btn').innerText = isRegisterMode ? "Daftar" : "Masuk";
            document.getElementById('auth-switch-btn').innerText = isRegisterMode ? "Sudah punya akun? Masuk" : "Belum punya akun? Daftar";
        }

        window.handleAuth = function() {
            const email = document.getElementById('email-input').value.trim();
            const password = document.getElementById('password-input').value.trim();
            if (!email || !password) { alert('Email dan password harus diisi!'); return; }

            if (isRegisterMode) {
                createUserWithEmailAndPassword(auth, email, password)
                    .then(() => { alert('Registrasi berhasil!'); })
                    .catch((error) => { alert('Gagal daftar: ' + error.message); });
            } else {
                signInWithEmailAndPassword(auth, email, password)
                    .then(() => {})
                    .catch((error) => { alert('Gagal masuk: ' + error.message); });
            }
        }

        window.logout = function() { signOut(auth).then(() => { location.reload(); }); }

        function generateUniqueId(email) {
            let hash = 0;
            for (let i = 0; i < email.length; i++) { hash = email.charCodeAt(i) + ((hash << 5) - hash); }
            const chars = "ABCDEFGHIJKLMNOPQRSTUVWXYZ0123456789";
            let pin = "FI";
            for (let i = 0; i < 5; i++) { pin += chars[Math.abs((hash + i * 7) % chars.length)]; }
            return pin;
        }

        onAuthStateChanged(auth, (user) => {
            if (user) {
                document.getElementById('auth-screen').style.display = 'none';
                const userPin = generateUniqueId(user.email);
                document.getElementById('my-active-pin').innerText = userPin;
                loadUserProfile(user.email);
                initPeerChatSystem(userPin, user.email);
            }
        });
    </script>

    <!-- SCRIPT UTAMA & WHATSAPP STATUS REPLY SYSTEM -->
    <script>
        let peer = null;
        let connections = {};
        let activeChatPeerId = null;
        let myUserId = null;
        let currentUserEmail = '';
        let activeViewerStory = null;

        function switchTab(tabId, el) {
            document.querySelectorAll('.tab-content').forEach(tab => tab.classList.remove('active'));
            document.querySelectorAll('.nav-item').forEach(nav => nav.classList.remove('active'));
            document.getElementById(tabId).classList.add('active');
            if(el) el.classList.add('active');
            if(tabId === 'tab-chat') renderChatRooms();
            if(tabId === 'tab-friends') renderFriendsList();
            if(tabId === 'tab-status') renderWhatsAppStatusUI();
        }

        function goToFriendsTab() {
            switchTab('tab-friends', document.getElementById('nav-item-friends'));
        }

        function loadUserProfile(email) {
            currentUserEmail = email;
            const savedName = localStorage.getItem('profile_name_' + email) || email.split('@')[0];
            const savedAvatar = localStorage.getItem('profile_avatar_' + email) || '';

            document.getElementById('profile-name-input').value = savedName;
            if (savedAvatar) {
                document.getElementById('profile-preview').src = savedAvatar;
                document.getElementById('my-status-avatar').src = savedAvatar;
                const headerAvatar = document.getElementById('header-avatar-img');
                headerAvatar.src = savedAvatar;
                headerAvatar.style.display = 'block';
            }
            renderWhatsAppStatusUI();
        }

        function saveProfileName() {
            const newName = document.getElementById('profile-name-input').value.trim();
            if (newName) {
                localStorage.setItem('profile_name_' + currentUserEmail, newName);
                document.getElementById('header-peer-title').innerText = newName;
                alert('Nama pengguna berhasil disimpan!');
            }
        }

        function handleAvatarSelect(event) {
            const file = event.target.files[0];
            if (!file) return;
            const reader = new FileReader();
            reader.onload = function(e) {
                const base64Img = e.target.result;
                localStorage.setItem('profile_avatar_' + currentUserEmail, base64Img);
                document.getElementById('profile-preview').src = base64Img;
                document.getElementById('my-status-avatar').src = base64Img;
                const headerAvatar = document.getElementById('header-avatar-img');
                headerAvatar.src = base64Img;
                headerAvatar.style.display = 'block';
                renderWhatsAppStatusUI();
                alert('Foto profil berhasil diperbarui!');
            };
            reader.readAsDataURL(file);
        }

        function initPeerChatSystem(pinId, emailAccount) {
            myUserId = pinId;
            peer = new Peer(myUserId);

            peer.on('open', (id) => {
                document.getElementById('header-status').innerText = 'Online';
            });

            peer.on('connection', (conn) => {
                setupIncomingConnection(conn);
                saveAutoContact(conn.peer);
            });

            peer.on('call', (call) => {
                const accept = confirm(`Panggilan masuk dari ID: ${call.peer}. Terima?`);
                if (!accept) { call.close(); return; }
                const isVideo = confirm("Aktifkan kamera Anda juga?");
                navigator.mediaDevices.getUserMedia({ video: isVideo, audio: true })
                    .then((stream) => {
                        localStream = stream;
                        localVideo.srcObject = stream;
                        localVideo.style.display = isVideo ? 'block' : 'none';
                        mediaCall = call;
                        call.answer(stream);
                        setupCallHandlers();
                        document.getElementById('call-box').classList.add('active');
                    });
            });

            renderFriendsList();
            renderChatRooms();
            renderWhatsAppStatusUI();
        }

        function setupIncomingConnection(conn) {
            connections[conn.peer] = conn;
            conn.on('data', (data) => { handleIncomingData(conn.peer, data); });
            conn.on('close', () => { delete connections[conn.peer]; });
            renderChatRooms();
        }

        function addNewFriendId() {
            const peerId = document.getElementById('manual-peer-input').value.trim().toUpperCase();
            if (!peerId) { alert('Masukkan ID Teman!'); return; }
            if (peerId === myUserId) { alert('Tidak bisa menambahkan ID sendiri!'); return; }
            
            document.getElementById('manual-peer-input').value = '';
            connectToPeer(peerId, true);
        }

        function connectToPeer(peerId, openChatAfter = false) {
            if (connections[peerId] && connections[peerId].open) {
                saveAutoContact(peerId);
                if (openChatAfter) {
                    switchTab('tab-chat', document.getElementById('nav-item-chat'));
                    openChatRoom(peerId);
                }
                return;
            }

            const conn = peer.connect(peerId);
            conn.on('open', () => {
                connections[peerId] = conn;
                setupIncomingConnection(conn);
                saveAutoContact(peerId);
                if (openChatAfter) {
                    switchTab('tab-chat', document.getElementById('nav-item-chat'));
                    openChatRoom(peerId);
                } else {
                    alert('Berhasil terhubung ke ID: ' + peerId);
                }
            });
            conn.on('error', () => { alert('Gagal terhubung ke ID tersebut. Pastikan ID aktif.'); });
        }

        function openChatRoom(peerId) {
            activeChatPeerId = peerId;
            document.getElementById('active-chat-name').innerText = 'ID: ' + peerId;
            document.getElementById('chat-list-view').style.display = 'none';
            document.getElementById('chat-room-view').classList.add('active');
            renderActiveChatMessages(peerId);
            document.getElementById('btn-voice-call').disabled = false;
            document.getElementById('btn-video-call').disabled = false;
        }

        function closeChatRoom() {
            activeChatPeerId = null;
            document.getElementById('chat-room-view').classList.remove('active');
            document.getElementById('chat-list-view').style.display = 'flex';
            renderChatRooms();
            document.getElementById('btn-voice-call').disabled = true;
            document.getElementById('btn-video-call').disabled = true;
        }

        function renderChatRooms() {
            const container = document.getElementById('chat-rooms-container');
            let contacts = JSON.parse(localStorage.getItem('fi_chat_contacts') || '[]');
            container.innerHTML = '';

            if (contacts.length === 0) {
                container.innerHTML = '<div style="font-size: 0.85rem; color: #888; text-align: center; padding: 30px;">Belum ada percakapan.<br>Klik tombol <strong>+ Tambah Chat</strong> di atas.</div>';
                return;
            }

            contacts.forEach((peerId) => {
                let msgs = JSON.parse(localStorage.getItem('chat_msgs_' + peerId) || '[]');
                let lastMsg = msgs.length > 0 ? (msgs[msgs.length - 1].message || '[File/Gambar]') : 'Mulai percakapan...';

                const div = document.createElement('div');
                div.className = 'chat-room-item';
                div.onclick = () => openChatRoom(peerId);
                div.innerHTML = `
                    <div class="chat-room-avatar">${peerId.substring(0,2)}</div>
                    <div style="flex:1; min-width:0;">
                        <strong>ID: ${peerId}</strong>
                        <p style="font-size: 0.8rem; color: #64748b; white-space: nowrap; overflow: hidden; text-overflow: ellipsis;">${lastMsg}</p>
                    </div>
                `;
                container.appendChild(div);
            });
        }

        function renderActiveChatMessages(peerId) {
            const chatBox = document.getElementById('active-chat-box');
            chatBox.innerHTML = '';
            let msgs = JSON.parse(localStorage.getItem('chat_msgs_' + peerId) || '[]');
            msgs.forEach(m => { appendMsgElement(m.text, m.type, m.isImage, m.fileName); });
            chatBox.scrollTop = chatBox.scrollHeight;
        }

        function handleIncomingData(peerId, data) {
            let msgs = JSON.parse(localStorage.getItem('chat_msgs_' + peerId) || '[]');
            if (data.type === 'chat') {
                msgs.push({ text: data.message, type: 'peer', isImage: false });
            } else if (data.type === 'file') {
                msgs.push({ text: data.fileContent, type: 'peer', isImage: data.fileType.startsWith('image/'), fileName: data.fileName });
            }
            localStorage.setItem('chat_msgs_' + peerId, JSON.stringify(msgs));

            if (activeChatPeerId === peerId) { renderActiveChatMessages(peerId); }
            renderChatRooms();
        }

        function sendMessage() {
            const text = document.getElementById('chat-input').value.trim();
            if (!text || !activeChatPeerId) return;

            const conn = connections[activeChatPeerId];
            if (conn && conn.open) {
                conn.send({ type: 'chat', message: text });
                saveAndDisplayMsg(activeChatPeerId, text, 'self', false);
                document.getElementById('chat-input').value = '';
            } else {
                alert('Koneksi terputus. Hubungkan kembali dari menu Kontak.');
            }
        }

        function handleFileSelect(event) {
            const file = event.target.files[0];
            if (!file || !activeChatPeerId) return;
            if (file.size > 5 * 1024 * 1024) { alert('Maksimal ukuran file 5MB.'); return; }

            const reader = new FileReader();
            reader.onload = function(e) {
                const fileData = { type: 'file', fileName: file.name, fileType: file.type, fileContent: e.target.result };
                const conn = connections[activeChatPeerId];
                if (conn && conn.open) {
                    conn.send(fileData);
                    saveAndDisplayMsg(activeChatPeerId, fileData.fileContent, 'self', fileData.fileType.startsWith('image/'), fileData.fileName);
                }
            };
            reader.readAsDataURL(file);
            event.target.value = '';
        }

        function saveAndDisplayMsg(peerId, text, type, isImage, fileName = '') {
            let msgs = JSON.parse(localStorage.getItem('chat_msgs_' + peerId) || '[]');
            msgs.push({ text, type, isImage, fileName });
            localStorage.setItem('chat_msgs_' + peerId, JSON.stringify(msgs));
            renderActiveChatMessages(peerId);
            renderChatRooms();
        }

        function appendMsgElement(text, type, isImage, fileName = '') {
            const chatBox = document.getElementById('active-chat-box');
            const row = document.createElement('div');
            row.className = `msg-row ${type === 'self' ? 'row-out' : 'row-in'}`;
            const bubble = document.createElement('div');
            bubble.className = `bubble ${type === 'self' ? 'bubble-out' : 'bubble-in'}`;

            if (isImage) {
                const img = document.createElement('img');
                img.src = text; bubble.appendChild(img);
            } else if (fileName) {
                const link = document.createElement('a');
                link.href = text; link.download = fileName; link.className = 'file-attachment';
                link.innerHTML = `📄 <span>${fileName}</span>`; bubble.appendChild(link);
            } else {
                bubble.innerText = text;
            }

            row.appendChild(bubble);
            chatBox.appendChild(row);
            chatBox.scrollTop = chatBox.scrollHeight;
        }

        function handleKeyPress(e) { if (e.key === 'Enter') sendMessage(); }

        function saveAutoContact(peerId) {
            let contacts = JSON.parse(localStorage.getItem('fi_chat_contacts') || '[]');
            if (!contacts.includes(peerId)) {
                contacts.push(peerId);
                localStorage.setItem('fi_chat_contacts', JSON.stringify(contacts));
                renderFriendsList();
            }
        }

        function renderFriendsList() {
            const container = document.getElementById('friends-list-container');
            let contacts = JSON.parse(localStorage.getItem('fi_chat_contacts') || '[]');
            container.innerHTML = '';

            if (contacts.length === 0) {
                container.innerHTML = '<div style="font-size: 0.8rem; color: #888; text-align: center;">Belum ada kontak. Tambahkan ID di atas.</div>';
                return;
            }

            contacts.forEach((peerId, idx) => {
                const div = document.createElement('div');
                div.className = 'friend-card';
                div.innerHTML = `
                    <div class="friend-info"><strong>ID Teman</strong><small>${peerId}</small></div>
                    <div class="friend-actions">
                        <button class="btn-sm" onclick="switchTab('tab-chat', document.getElementById('nav-item-chat')); openChatRoom('${peerId}');">Chat</button>
                        <button class="btn-sm btn-sm-danger" onclick="removeContact(${idx})">Hapus</button>
                    </div>
                `;
                container.appendChild(div);
            });
        }

        function removeContact(index) {
            let contacts = JSON.parse(localStorage.getItem('fi_chat_contacts') || '[]');
            contacts.splice(index, 1);
            localStorage.setItem('fi_chat_contacts', JSON.stringify(contacts));
            renderFriendsList();
            renderChatRooms();
        }

        // ==========================================
        // SISTEM STATUS & BALAS KE CHAT UTAMA
        // ==========================================
        function handleMyStatusClick() {
            let statuses = JSON.parse(localStorage.getItem('fi_chat_statuses') || '[]');
            let myName = localStorage.getItem('profile_name_' + currentUserEmail) || 'Saya';
            let myStatuses = statuses.filter(s => s.name === myName);

            if (myStatuses.length > 0) {
                openStatusViewer(myStatuses[0].id);
            } else {
                let choice = prompt("Pilih tipe status:\n1. Ketik Teks\n2. Unggah Gambar", "1");
                if (choice === "1") {
                    let txt = prompt("Masukkan teks status Anda:");
                    if (txt) { saveStatusItem({ type: 'text', content: txt }); renderWhatsAppStatusUI(); }
                } else if (choice === "2") {
                    document.getElementById('status-media-input').click();
                }
            }
        }

        function postMediaStatus(event) {
            const file = event.target.files[0];
            if (!file) return;
            const reader = new FileReader();
            reader.onload = function(e) {
                saveStatusItem({ type: 'image', content: e.target.result });
                renderWhatsAppStatusUI();
                alert('Status gambar berhasil dibagikan!');
            };
            reader.readAsDataURL(file);
            event.target.value = '';
        }

        function saveStatusItem(statusData) {
            const userName = localStorage.getItem('profile_name_' + currentUserEmail) || 'Saya';
            const userAvatar = localStorage.getItem('profile_avatar_' + currentUserEmail) || '';
            let statuses = JSON.parse(localStorage.getItem('fi_chat_statuses') || '[]');
            
            statuses.unshift({
                id: Date.now(), peerId: myUserId, name: userName, avatar: userAvatar, type: statusData.type, content: statusData.content,
                likes: 0, time: new Date().toLocaleTimeString([], {hour: '2-digit', minute:'2-digit'})
            });
            localStorage.setItem('fi_chat_statuses', JSON.stringify(statuses));
        }

        function renderWhatsAppStatusUI() {
            let statuses = JSON.parse(localStorage.getItem('fi_chat_statuses') || '[]');
            let myName = localStorage.getItem('profile_name_' + currentUserEmail) || 'Saya';
            let myAvatar = localStorage.getItem('profile_avatar_' + currentUserEmail) || '';

            let myRing = document.getElementById('my-status-ring-container');
            let myBadge = document.getElementById('my-status-badge');
            let mySubtitle = document.getElementById('my-status-subtitle');
            let myHasStatus = statuses.some(s => s.name === myName);

            document.getElementById('my-status-avatar').src = myAvatar;
            if (myHasStatus) {
                myRing.className = "wa-status-ring has-status";
                myBadge.style.display = 'none';
                mySubtitle.innerText = "Ketuk untuk melihat status Anda";
            } else {
                myRing.className = "wa-status-ring no-status";
                myBadge.style.display = 'flex';
                mySubtitle.innerText = "Ketuk untuk menambah status";
            }

            let listContainer = document.getElementById('wa-status-list-container');
            listContainer.innerHTML = '';

            let otherStatuses = statuses.filter(s => s.name !== myName);
            if (otherStatuses.length === 0) {
                listContainer.innerHTML = '<div style="font-size: 0.85rem; color: #667781; padding: 12px 16px;">Tidak ada pembaruan status baru</div>';
                return;
            }

            let grouped = {};
            otherStatuses.forEach(st => {
                if (!grouped[st.name]) grouped[st.name] = st;
            });

            Object.values(grouped).forEach(st => {
                let div = document.createElement('div');
                div.className = 'wa-status-item';
                div.onclick = () => openStatusViewer(st.id);
                div.innerHTML = `
                    <div class="wa-status-ring has-status">
                        <img class="wa-status-avatar" src="${st.avatar || ''}">
                    </div>
                    <div>
                        <strong style="color:#111b21;">${st.name}</strong><br>
                        <span style="font-size:0.8rem; color:#667781;">Hari ini pukul ${st.time}</span>
                    </div>
                `;
                listContainer.appendChild(div);
            });
        }

        function openStatusViewer(statusId) {
            let statuses = JSON.parse(localStorage.getItem('fi_chat_statuses') || '[]');
            let st = statuses.find(s => s.id === statusId);
            if (!st) return;

            activeViewerStory = st;
            document.getElementById('viewer-author-name').innerText = st.name;
            document.getElementById('viewer-author-avatar').src = st.avatar || '';
            document.getElementById('viewer-time').innerText = st.time;
            document.getElementById('viewer-like-btn').innerText = `❤️️ Suka (${st.likes})`;

            let contentBox = document.getElementById('story-content-box');
            contentBox.innerHTML = '';
            if (st.type === 'image') {
                contentBox.innerHTML = `<img src="${st.content}" class="story-image-display">`;
            } else {
                contentBox.innerHTML = `<div class="story-text-display">${st.content}</div>`;
            }

            let progContainer = document.getElementById('story-progress-container');
            progContainer.innerHTML = '<div class="story-progress-segment"><div class="story-progress-fill" id="story-fill"></div></div>';
            setTimeout(() => {
                let fill = document.getElementById('story-fill');
                if (fill) { fill.style.transitionDuration = '6s'; fill.style.width = '100%'; }
            }, 50);

            document.getElementById('status-viewer-modal').style.display = 'flex';
        }

        function closeStatusViewer() {
            document.getElementById('status-viewer-modal').style.display = 'none';
            activeViewerStory = null;
        }

        function likeActiveStory() {
            if (!activeViewerStory) return;
            let statuses = JSON.parse(localStorage.getItem('fi_chat_statuses') || '[]');
            let st = statuses.find(s => s.id === activeViewerStory.id);
            if (st) {
                st.likes++;
                localStorage.setItem('fi_chat_statuses', JSON.stringify(statuses));
                document.getElementById('viewer-like-btn').innerText = `❤️ Suka (${st.likes})`;
            }
        }

        // Mengirim balasan status langsung ke chat utama pemilik status
        function replyStatusToMainChat() {
            let input = document.getElementById('viewer-comment-input');
            let text = input.value.trim();
            if (!text || !activeViewerStory) return;

            let targetPeerId = activeViewerStory.peerId;
            if (!targetPeerId) {
                alert('Tidak dapat membalas status akun ini (ID tidak ditemukan).');
                return;
            }

            let replyMessage = `Membalas status: "${activeViewerStory.type === 'text' ? activeViewerStory.content : '[Foto]'}"\n👉 ${text}`;

            // Simpan otomatis ke riwayat chat & kirim via P2P jika terhubung
            saveAutoContact(targetPeerId);
            let conn = connections[targetPeerId];
            if (conn && conn.open) {
                conn.send({ type: 'chat', message: replyMessage });
            }
            saveAndDisplayMsg(targetPeerId, replyMessage, 'self', false);

            input.value = '';
            closeStatusViewer();

            // Pindah langsung ke tab chat dan buka ruang chat teman tersebut
            switchTab('tab-chat', document.getElementById('nav-item-chat'));
            openChatRoom(targetPeerId);
        }

        // Panggilan Video/Suara
        let mediaCall = null;
        let localStream = null;
        function startCall(withVideo) {
            if (!activeChatPeerId || !connections[activeChatPeerId]) { alert('Pilih chat teman terlebih dahulu!'); return; }
            navigator.mediaDevices.getUserMedia({ video: withVideo, audio: true })
                .then((stream) => {
                    localStream = stream;
                    localVideo.srcObject = stream;
                    localVideo.style.display = withVideo ? 'block' : 'none';
                    mediaCall = peer.call(activeChatPeerId, stream);
                    setupCallHandlers();
                    document.getElementById('call-box').classList.add('active');
                });
        }
        function setupCallHandlers() {
            mediaCall.on('stream', (remoteStream) => { remoteVideo.srcObject = remoteStream; });
            mediaCall.on('close', () => { endCall(); });
        }
        function toggleAudio() {
            if (localStream) { const tr = localStream.getAudioTracks()[0]; if(tr) tr.enabled = !tr.enabled; }
        }
        function toggleVideo() {
            if (localStream) { const tr = localStream.getVideoTracks()[0]; if(tr) tr.enabled = !tr.enabled; }
        }
        function endCall() {
            if (mediaCall) { mediaCall.close(); mediaCall = null; }
            if (localStream) { localStream.getTracks().forEach(t => t.stop()); localStream = null; }
            document.getElementById('call-box').classList.remove('active');
        }
    </script>
</body>
</html>
