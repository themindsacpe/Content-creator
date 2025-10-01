<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>MindScape | THE POWER OF THOUGHTS AND IMAGINATION</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <link href="https://fonts.googleapis.com/css2?family=Playfair+Display:wght@400;500;600;700&family=Inter:wght@300;400;500;600;700&display=swap" rel="stylesheet">
    <style>
        /* === CSS VARIABLES === */
        :root {
            --primary: #1a1a2e;
            --secondary: #16213e;
            --accent: #e94560;
            --accent-light: #ff6b9d;
            --light: #f8f9fa;
            --dark: #0f3460;
            --text: #2d3748;
            --text-light: #718096;
            --white: #ffffff;
            --success: #38b2ac;
            --warning: #ed8936;
            --danger: #e53e3e;
            --shadow: 0 8px 30px rgba(0, 0, 0, 0.12);
            --shadow-lg: 0 20px 60px rgba(0, 0, 0, 0.15);
            --transition: all 0.4s cubic-bezier(0.25, 0.46, 0.45, 0.94);
            --border-radius: 16px;
            --sidebar-width: 280px;
            --header-height: 80px;
            --gradient-primary: linear-gradient(135deg, var(--primary) 0%, var(--secondary) 100%);
            --gradient-accent: linear-gradient(135deg, var(--accent) 0%, var(--accent-light) 100%);
            --gradient-card: linear-gradient(135deg, #ffffff 0%, #f8fafc 100%);
        }

        /* === BASE STYLES === */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        html {
            scroll-behavior: smooth;
        }

        body {
            font-family: 'Inter', sans-serif;
            line-height: 1.7;
            color: var(--text);
            background: linear-gradient(135deg, #f5f7fa 0%, #c3cfe2 100%);
            min-height: 100vh;
            overflow-x: hidden;
        }

        body.dark-mode {
            background: linear-gradient(135deg, #0f0f23 0%, #1a1a2e 100%);
            color: #e2e8f0;
        }

        h1, h2, h3, h4, h5 {
            font-family: 'Playfair Display', serif;
            margin-bottom: 1.5rem;
            color: var(--primary);
            line-height: 1.3;
            font-weight: 600;
        }

        body.dark-mode h1,
        body.dark-mode h2,
        body.dark-mode h3,
        body.dark-mode h4,
        body.dark-mode h5 {
            color: #f7fafc;
        }

        h1 {
            font-size: 3.5rem;
            background: var(--gradient-accent);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }

        h2 {
            font-size: 2.75rem;
        }

        h3 {
            font-size: 1.875rem;
        }

        p {
            margin-bottom: 1.5rem;
            color: var(--text);
            font-size: 1.1rem;
        }

        body.dark-mode p {
            color: #e2e8f0;
        }

        a {
            text-decoration: none;
            color: var(--accent);
            transition: var(--transition);
            font-weight: 500;
        }

        a:hover {
            color: var(--accent-light);
        }

        img {
            max-width: 100%;
            height: auto;
            border-radius: var(--border-radius);
            transition: var(--transition);
        }

        .container {
            width: 90%;
            max-width: 1200px;
            margin: 0 auto;
        }

        .btn {
            display: inline-flex;
            align-items: center;
            gap: 10px;
            padding: 14px 28px;
            background: var(--gradient-accent);
            color: var(--white);
            border: none;
            border-radius: 50px;
            cursor: pointer;
            font-weight: 600;
            font-size: 1rem;
            transition: var(--transition);
            text-align: center;
            box-shadow: var(--shadow);
            position: relative;
            overflow: hidden;
        }

        .btn::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(255,255,255,0.2), transparent);
            transition: left 0.5s;
        }

        .btn:hover::before {
            left: 100%;
        }

        .btn:hover {
            transform: translateY(-3px);
            box-shadow: var(--shadow-lg);
        }

        .btn-accent {
            background: var(--gradient-accent);
        }

        .btn-success {
            background: linear-gradient(135deg, var(--success), #4fd1c7);
        }

        .btn-warning {
            background: linear-gradient(135deg, var(--warning), #f6ad55);
        }

        .btn-danger {
            background: linear-gradient(135deg, var(--danger), #fc8181);
        }

        .btn-outline {
            background: transparent;
            border: 2px solid var(--accent);
            color: var(--accent);
        }

        .btn-outline:hover {
            background: var(--accent);
            color: var(--white);
        }

        .btn-sm {
            padding: 10px 20px;
            font-size: 0.9rem;
        }

        .btn-lg {
            padding: 18px 36px;
            font-size: 1.1rem;
        }

        .btn-block {
            display: flex;
            width: 100%;
            justify-content: center;
        }

        .section {
            padding: 8rem 0;
            position: relative;
        }

        .section-title {
            text-align: center;
            margin-bottom: 5rem;
            position: relative;
        }

        .section-title::after {
            content: '';
            display: block;
            width: 120px;
            height: 4px;
            background: var(--gradient-accent);
            margin: 1.5rem auto;
            border-radius: 2px;
        }

        .card {
            background: var(--gradient-card);
            border-radius: var(--border-radius);
            box-shadow: var(--shadow);
            overflow: hidden;
            transition: var(--transition);
            border: 1px solid rgba(255, 255, 255, 0.3);
            backdrop-filter: blur(20px);
            position: relative;
        }

        body.dark-mode .card {
            background: linear-gradient(135deg, #2d3748 0%, #4a5568 100%);
            border: 1px solid rgba(255, 255, 255, 0.1);
        }

        .card:hover {
            transform: translateY(-10px);
            box-shadow: var(--shadow-lg);
        }

        .card::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            height: 4px;
            background: var(--gradient-accent);
            transform: scaleX(0);
            transition: transform 0.3s ease;
        }

        .card:hover::before {
            transform: scaleX(1);
        }

        .text-center { text-align: center; }
        .text-right { text-align: right; }
        .text-muted { color: var(--text-light); }

        body.dark-mode .text-muted {
            color: #a0aec0;
        }

        .mb-0 { margin-bottom: 0; }
        .mb-1 { margin-bottom: 0.75rem; }
        .mb-2 { margin-bottom: 1.5rem; }
        .mb-3 { margin-bottom: 2rem; }
        .mb-4 { margin-bottom: 3rem; }

        .mt-1 { margin-top: 0.75rem; }
        .mt-2 { margin-top: 1.5rem; }
        .mt-3 { margin-top: 2rem; }
        .mt-4 { margin-top: 3rem; }

        .d-flex { display: flex; }
        .justify-content-between { justify-content: space-between; }
        .align-items-center { align-items: center; }
        .w-100 { width: 100%; }

        .badge {
            display: inline-flex;
            align-items: center;
            gap: 6px;
            padding: 8px 16px;
            background: var(--gradient-accent);
            color: var(--white);
            border-radius: 20px;
            font-size: 0.8rem;
            font-weight: 600;
            text-transform: uppercase;
            letter-spacing: 0.5px;
        }

        .badge-primary { background: var(--gradient-primary); }
        .badge-secondary { background: linear-gradient(135deg, #4a5568, #718096); }
        .badge-success { background: linear-gradient(135deg, var(--success), #4fd1c7); }

        .hidden { display: none !important; }

        /* === HEADER STYLES === */
        header {
            background: rgba(255, 255, 255, 0.95);
            backdrop-filter: blur(20px);
            box-shadow: var(--shadow);
            position: sticky;
            top: 0;
            z-index: 1000;
            border-bottom: 1px solid rgba(255, 255, 255, 0.3);
            transition: var(--transition);
        }

        body.dark-mode header {
            background: rgba(26, 32, 44, 0.95);
            border-bottom: 1px solid rgba(255, 255, 255, 0.1);
        }

        .header-container {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 1.5rem 0;
        }

        .logo {
            font-family: 'Playfair Display', serif;
            font-size: 2.25rem;
            font-weight: 700;
            color: var(--primary);
            display: flex;
            align-items: center;
            gap: 12px;
        }

        body.dark-mode .logo {
            color: #f7fafc;
        }

        .logo i {
            color: var(--accent);
            font-size: 2.5rem;
        }

        .nav-menu {
            display: flex;
            list-style: none;
            gap: 2.5rem;
            align-items: center;
        }

        .nav-menu a {
            color: var(--primary);
            font-weight: 500;
            padding: 10px 20px;
            border-radius: 25px;
            transition: var(--transition);
            position: relative;
        }

        body.dark-mode .nav-menu a {
            color: #f7fafc;
        }

        .nav-menu a:hover {
            background: var(--gradient-accent);
            color: var(--white);
            transform: translateY(-2px);
        }

        .mobile-toggle {
            display: none;
            font-size: 1.5rem;
            cursor: pointer;
            color: var(--primary);
            transition: var(--transition);
        }

        body.dark-mode .mobile-toggle {
            color: #f7fafc;
        }

        /* === HERO SECTION === */
        .hero {
            background: var(--gradient-primary);
            color: var(--white);
            text-align: center;
            padding: 12rem 0;
            position: relative;
            overflow: hidden;
        }

        .hero::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background: url('data:image/svg+xml,<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 1000 1000"><polygon fill="%23ffffff08" points="0,1000 1000,0 1000,1000"/></svg>');
            animation: float 6s ease-in-out infinite;
        }

        @keyframes float {
            0%, 100% { transform: translateY(0px); }
            50% { transform: translateY(-20px); }
        }

        .hero h1 {
            font-size: 4.5rem;
            margin-bottom: 2rem;
            color: var(--white);
            text-shadow: 2px 2px 4px rgba(0,0,0,0.3);
            -webkit-text-fill-color: var(--white);
            background: none;
        }

        .hero p {
            font-size: 1.4rem;
            max-width: 700px;
            margin: 0 auto 4rem;
            opacity: 0.9;
            color: var(--white);
        }

        .hero-buttons {
            display: flex;
            gap: 1.5rem;
            justify-content: center;
            flex-wrap: wrap;
        }

        /* === FEATURED ARTICLES === */
        .featured-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(380px, 1fr));
            gap: 3rem;
        }

        .featured-article {
            position: relative;
            height: 450px;
            border-radius: var(--border-radius);
            overflow: hidden;
            cursor: pointer;
            box-shadow: var(--shadow);
        }

        .featured-article img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            transition: var(--transition);
        }

        .featured-article:hover img {
            transform: scale(1.1);
        }

        .featured-content {
            position: absolute;
            bottom: 0;
            left: 0;
            right: 0;
            background: linear-gradient(transparent, rgba(0, 0, 0, 0.9));
            color: var(--white);
            padding: 2.5rem;
            transform: translateY(10px);
            transition: var(--transition);
        }

        .featured-article:hover .featured-content {
            transform: translateY(0);
        }

        .featured-content h3 {
            color: var(--white);
            margin-bottom: 1rem;
            font-size: 1.5rem;
        }

        /* === ARTICLES GRID === */
        .articles-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(420px, 1fr));
            gap: 3rem;
        }

        .article-card {
            display: flex;
            flex-direction: column;
            height: 100%;
            cursor: pointer;
        }

        .article-img {
            height: 280px;
            overflow: hidden;
            border-radius: var(--border-radius) var(--border-radius) 0 0;
        }

        .article-img img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            transition: var(--transition);
        }

        .article-card:hover .article-img img {
            transform: scale(1.1);
        }

        .article-content {
            padding: 2.5rem;
            flex-grow: 1;
            display: flex;
            flex-direction: column;
        }

        .article-meta {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-top: auto;
            padding-top: 1.5rem;
            border-top: 1px solid rgba(0, 0, 0, 0.1);
            font-size: 0.9rem;
            color: var(--text-light);
        }

        body.dark-mode .article-meta {
            border-top: 1px solid rgba(255, 255, 255, 0.1);
        }

        /* === ADMIN PANEL STYLES === */
        .admin-panel {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background: var(--light);
            z-index: 2000;
            overflow-y: auto;
        }

        body.dark-mode .admin-panel {
            background: #1a202c;
        }

        .admin-header {
            background: var(--gradient-primary);
            color: var(--white);
            padding: 1.5rem 0;
            box-shadow: var(--shadow);
        }

        .admin-header-container {
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .admin-logo {
            font-family: 'Playfair Display', serif;
            font-size: 1.8rem;
            font-weight: 700;
            display: flex;
            align-items: center;
            gap: 12px;
        }

        .admin-main {
            display: flex;
            min-height: calc(100vh - 80px);
        }

        .admin-sidebar {
            width: var(--sidebar-width);
            background: var(--white);
            box-shadow: var(--shadow);
            padding: 2.5rem 0;
        }

        body.dark-mode .admin-sidebar {
            background: #2d3748;
        }

        .sidebar-menu {
            list-style: none;
        }

        .sidebar-menu a {
            display: flex;
            align-items: center;
            gap: 15px;
            padding: 1.25rem 2.5rem;
            color: var(--text);
            transition: var(--transition);
            border-left: 4px solid transparent;
            font-weight: 500;
        }

        body.dark-mode .sidebar-menu a {
            color: #e2e8f0;
        }

        .sidebar-menu a:hover,
        .sidebar-menu a.active {
            background: rgba(233, 69, 96, 0.1);
            color: var(--accent);
            border-left-color: var(--accent);
        }

        .admin-content {
            flex: 1;
            padding: 3rem;
            background: #f8fafc;
        }

        body.dark-mode .admin-content {
            background: #1a202c;
        }

        .admin-section {
            display: none;
            background: var(--white);
            border-radius: var(--border-radius);
            box-shadow: var(--shadow);
            padding: 3rem;
            margin-bottom: 2rem;
            animation: fadeInUp 0.6s ease;
        }

        body.dark-mode .admin-section {
            background: #2d3748;
        }

        .admin-section.active {
            display: block;
        }

        @keyframes fadeInUp {
            from {
                opacity: 0;
                transform: translateY(30px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        .form-group {
            margin-bottom: 2rem;
        }

        .form-label {
            display: block;
            margin-bottom: 0.75rem;
            font-weight: 600;
            color: var(--primary);
            font-size: 1.1rem;
        }

        body.dark-mode .form-label {
            color: #f7fafc;
        }

        .form-control {
            width: 100%;
            padding: 1.25rem 1.5rem;
            border: 2px solid #e2e8f0;
            border-radius: var(--border-radius);
            font-size: 1rem;
            transition: var(--transition);
            background: var(--white);
            font-family: 'Inter', sans-serif;
        }

        body.dark-mode .form-control {
            background: #4a5568;
            border-color: #718096;
            color: #f7fafc;
        }

        .form-control:focus {
            border-color: var(--accent);
            outline: none;
            box-shadow: 0 0 0 3px rgba(233, 69, 96, 0.1);
            transform: translateY(-2px);
        }

        textarea.form-control {
            min-height: 200px;
            resize: vertical;
            line-height: 1.6;
        }

        .file-upload {
            position: relative;
            border: 3px dashed #cbd5e0;
            border-radius: var(--border-radius);
            padding: 4rem 2rem;
            text-align: center;
            transition: var(--transition);
            cursor: pointer;
            background: rgba(233, 69, 96, 0.02);
        }

        body.dark-mode .file-upload {
            border-color: #718096;
            background: rgba(233, 69, 96, 0.05);
        }

        .file-upload:hover {
            border-color: var(--accent);
            background: rgba(233, 69, 96, 0.08);
            transform: translateY(-2px);
        }

        .file-upload-input {
            position: absolute;
            left: 0;
            top: 0;
            opacity: 0;
            width: 100%;
            height: 100%;
            cursor: pointer;
        }

        .preview-container {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(180px, 1fr));
            gap: 1.5rem;
            margin-top: 1.5rem;
        }

        .preview-item {
            position: relative;
            border-radius: var(--border-radius);
            overflow: hidden;
            box-shadow: var(--shadow);
            transition: var(--transition);
            aspect-r
