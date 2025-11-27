<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>KAVANA GS | Portfolio</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        /* ===== CSS Variables - Deep Blue Professional ===== */
        :root {
            --primary: #1e3a8a;
            --primary-dark: #1e40af;
            --secondary: #2563eb;
            --accent: #f59e0b;
            --light: #f1f5f9;
            --dark: #0f172a;
            --gray: #64748b;
            --max-width: 1200px;
            --border-radius: 12px;
            --transition: all 0.3s ease;
        }

        /* ===== Global Styles ===== */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }

        html {
            scroll-behavior: smooth;
        }

        body {
            background: var(--light);
            color: var(--dark);
            line-height: 1.6;
            overflow-x: hidden;
        }

        .container {
            max-width: var(--max-width);
            margin: 0 auto;
            padding: 0 20px;
        }

        section {
            padding: 80px 0;
        }

        h1, h2, h3, h4 {
            font-weight: 700;
            line-height: 1.2;
            margin-bottom: 1rem;
        }

        p {
            margin-bottom: 1rem;
        }

        .btn {
            display: inline-block;
            padding: 12px 28px;
            background: var(--primary);
            color: white;
            border-radius: 50px;
            font-weight: 600;
            text-decoration: none;
            transition: var(--transition);
            border: none;
            cursor: pointer;
            box-shadow: 0 4px 15px rgba(30, 58, 138, 0.3);
        }

        .btn:hover {
            background: var(--primary-dark);
            transform: translateY(-3px);
            box-shadow: 0 6px 20px rgba(30, 58, 138, 0.4);
        }

        .btn-secondary {
            background: transparent;
            border: 2px solid var(--primary);
            color: var(--primary);
        }

        .btn-secondary:hover {
            background: var(--primary);
            color: white;
        }

        .section-title {
            text-align: center;
            margin-bottom: 50px;
            position: relative;
        }

        .section-title h2 {
            font-size: 2.5rem;
            display: inline-block;
            color: var(--primary);
        }

        .section-title h2::after {
            content: '';
            position: absolute;
            width: 80px;
            height: 4px;
            background: var(--accent);
            bottom: -10px;
            left: 50%;
            transform: translateX(-50%);
            border-radius: 2px;
        }

        /* ===== Header & Navigation ===== */
        header {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            z-index: 1000;
            background: rgba(241, 245, 249, 0.95);
            backdrop-filter: blur(10px);
            padding: 20px 0;
            transition: var(--transition);
            box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
        }

        header.scrolled {
            padding: 15px 0;
        }

        .navbar {
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .logo {
            font-size: 1.8rem;
            font-weight: 700;
            color: var(--primary);
            text-decoration: none;
        }

        .logo span {
            color: var(--secondary);
        }

        .nav-links {
            display: flex;
            list-style: none;
        }

        .nav-links li {
            margin-left: 30px;
        }

        .nav-links a {
            color: var(--dark);
            text-decoration: none;
            font-weight: 500;
            transition: var(--transition);
            position: relative;
        }

        .nav-links a:hover {
            color: var(--primary);
        }

        .nav-links a::after {
            content: '';
            position: absolute;
            width: 0;
            height: 2px;
            background: var(--primary);
            bottom: -5px;
            left: 0;
            transition: var(--transition);
        }

        .nav-links a:hover::after {
            width: 100%;
        }

        .menu-toggle {
            display: none;
            font-size: 1.5rem;
            cursor: pointer;
            color: var(--primary);
        }

        /* ===== Hero Section ===== */
        .hero {
            height: 100vh;
            display: flex;
            align-items: center;
            position: relative;
            overflow: hidden;
            background: linear-gradient(135deg, var(--light) 0%, #e2e8f0 100%);
        }

        .hero-content {
            display: flex;
            align-items: center;
            justify-content: space-between;
            width: 100%;
        }

        .hero-text {
            flex: 1;
            max-width: 600px;
            z-index: 2;
        }

        .hero-text h1 {
            font-size: 3.5rem;
            margin-bottom: 20px;
            line-height: 1.1;
            color: var(--primary);
        }

        .hero-text h1 span {
            color: var(--secondary);
        }

        .hero-text p {
            font-size: 1.2rem;
            color: var(--gray);
            margin-bottom: 30px;
        }

        .hero-btns {
            display: flex;
            gap: 15px;
        }

        .hero-image {
            flex: 1;
            display: flex;
            justify-content: flex-end;
            z-index: 2;
        }

        .profile-photo {
            width: 400px;
            height: 400px;
            border-radius: 50%;
            object-fit: cover;
            border: 8px solid rgba(30, 58, 138, 0.2);
            box-shadow: 0 20px 40px rgba(0, 0, 0, 0.1);
            transition: var(--transition);
        }

        .profile-photo:hover {
            transform: scale(1.03);
            border-color: rgba(30, 58, 138, 0.4);
        }

        .scroll-down {
            position: absolute;
            bottom: 30px;
            left: 50%;
            transform: translateX(-50%);
            display: flex;
            flex-direction: column;
            align-items: center;
            color: var(--primary);
            text-decoration: none;
            font-weight: 500;
            z-index: 2;
            animation: bounce 2s infinite;
        }

        .scroll-down i {
            font-size: 1.5rem;
            margin-bottom: 5px;
        }

        @keyframes bounce {
            0%, 20%, 50%, 80%, 100% {
                transform: translateY(0) translateX(-50%);
            }
            40% {
                transform: translateY(-10px) translateX(-50%);
            }
            60% {
                transform: translateY(-5px) translateX(-50%);
            }
        }

        /* ===== About Section ===== */
        .about {
            background: white;
        }

        .about-content {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 50px;
            align-items: center;
        }

        .about-text h3 {
            font-size: 1.8rem;
            margin-bottom: 20px;
            color: var(--primary);
        }

        .about-text p {
            margin-bottom: 20px;
            color: var(--gray);
        }

        /* Social Links in About Section */
        .social-links {
            display: flex;
            gap: 15px;
            margin: 25px 0;
        }

        .social-link {
            display: flex;
            align-items: center;
            gap: 8px;
            padding: 10px 20px;
            background: rgba(30, 58, 138, 0.1);
            color: var(--primary);
            text-decoration: none;
            border-radius: 50px;
            font-weight: 500;
            transition: var(--transition);
        }

        .social-link:hover {
            background: var(--primary);
            color: white;
            transform: translateY(-3px);
        }

        .social-link i {
            font-size: 1.2rem;
        }

        .education {
            margin-top: 30px;
        }

        .education-item {
            margin-bottom: 25px;
            padding: 20px;
            background: var(--light);
            border-radius: var(--border-radius);
            border-left: 4px solid var(--primary);
            transition: var(--transition);
        }

        .education-item:hover {
            transform: translateX(5px);
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
        }

        .education-item h4 {
            font-size: 1.2rem;
            margin-bottom: 5px;
            color: var(--primary);
        }

        .education-item .date {
            color: var(--secondary);
            font-weight: 600;
            margin-bottom: 5px;
        }

        .education-item .percentage {
            color: var(--accent);
            font-weight: 600;
        }

        /* ===== Projects Section ===== */
        .projects-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(350px, 1fr));
            gap: 30px;
        }

        .project-card {
            background: white;
            border-radius: var(--border-radius);
            overflow: hidden;
            transition: var(--transition);
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.1);
            border: 1px solid #e2e8f0;
        }

        .project-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 15px 40px rgba(0, 0, 0, 0.15);
        }

        .project-img {
            height: 200px;
            background-size: cover;
            background-position: center;
        }

        .project-content {
            padding: 20px;
        }

        .project-content h3 {
            font-size: 1.3rem;
            margin-bottom: 10px;
            color: var(--primary);
        }

        .project-content p {
            color: var(--gray);
            margin-bottom: 15px;
            font-size: 0.95rem;
        }

        .project-tags {
            display: flex;
            flex-wrap: wrap;
            gap: 8px;
            margin-bottom: 15px;
        }

        .project-tags span {
            background: rgba(30, 58, 138, 0.1);
            color: var(--primary);
            padding: 5px 10px;
            border-radius: 20px;
            font-size: 0.8rem;
            font-weight: 500;
        }

        /* ===== Skills Section ===== */
        .skills {
            background: var(--light);
        }

        .skills-container {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
            gap: 30px;
        }

        .skill-category {
            background: white;
            padding: 25px;
            border-radius: var(--border-radius);
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.1);
            border: 1px solid #e2e8f0;
            transition: var(--transition);
        }

        .skill-category:hover {
            transform: translateY(-5px);
            box-shadow: 0 15px 40px rgba(0, 0, 0, 0.15);
        }

        .skill-category h3 {
            font-size: 1.3rem;
            margin-bottom: 20px;
            color: var(--primary);
            display: flex;
            align-items: center;
            gap: 10px;
        }

        .skill-category h3 i {
            font-size: 1.2rem;
            color: var(--secondary);
        }

        .skills-list {
            display: flex;
            flex-wrap: wrap;
            gap: 10px;
        }

        .skill-item {
            background: rgba(30, 58, 138, 0.1);
            color: var(--primary);
            padding: 8px 15px;
            border-radius: 20px;
            font-weight: 500;
            font-size: 0.9rem;
            transition: var(--transition);
        }

        .skill-item:hover {
            background: var(--primary);
            color: white;
            transform: translateY(-3px);
        }

        /* ===== Certificates Section ===== */
        .certificates-container {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(280px, 1fr));
            gap: 25px;
        }

        .certificate-card {
            background: white;
            border-radius: var(--border-radius);
            padding: 25px;
            text-align: center;
            transition: var(--transition);
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.1);
            border: 1px solid #e2e8f0;
        }

        .certificate-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 15px 40px rgba(0, 0, 0, 0.15);
        }

        .certificate-card i {
            font-size: 2.5rem;
            color: var(--primary);
            margin-bottom: 15px;
        }

        .certificate-card h3 {
            font-size: 1.2rem;
            margin-bottom: 10px;
            color: var(--primary);
        }

        .certificate-card p {
            color: var(--gray);
            font-size: 0.9rem;
            margin-bottom: 15px;
        }

        /* ===== Contact Section ===== */
        .contact {
            background: var(--light);
        }

        .contact-container {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 50px;
        }

        .contact-info {
            display: flex;
            flex-direction: column;
            gap: 25px;
        }

        .contact-item {
            display: flex;
            align-items: center;
            gap: 15px;
        }

        .contact-icon {
            width: 50px;
            height: 50px;
            background: var(--primary);
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 1.2rem;
            color: white;
        }

        .contact-details h4 {
            font-size: 1.1rem;
            margin-bottom: 5px;
            color: var(--primary);
        }

        .contact-details p {
            color: var(--gray);
        }

        .contact-form {
            background: white;
            padding: 30px;
            border-radius: var(--border-radius);
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.1);
            border: 1px solid #e2e8f0;
        }

        .form-group {
            margin-bottom: 20px;
        }

        .form-group label {
            display: block;
            margin-bottom: 8px;
            font-weight: 500;
            color: var(--primary);
        }

        .form-control {
            width: 100%;
            padding: 12px 15px;
            background: var(--light);
            border: 1px solid #cbd5e1;
            border-radius: 8px;
            color: var(--dark);
            font-size: 1rem;
            transition: var(--transition);
        }

        .form-control:focus {
            outline: none;
            border-color: var(--primary);
            box-shadow: 0 0 0 3px rgba(30, 58, 138, 0.2);
        }

        textarea.form-control {
            min-height: 150px;
            resize: vertical;
        }

        /* ===== Footer ===== */
        footer {
            background: var(--primary);
            padding: 50px 0 20px;
            color: white;
        }

        .footer-content {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 30px;
        }

        .footer-logo {
            font-size: 1.5rem;
            font-weight: 700;
            color: white;
        }

        .footer-logo span {
            color: var(--accent);
        }

        .footer-social-links {
            display: flex;
            gap: 15px;
        }

        .footer-social-link {
            width: 40px;
            height: 40px;
            background: rgba(255, 255, 255, 0.1);
            color: white;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            text-decoration: none;
            transition: var(--transition);
        }

        .footer-social-link:hover {
            background: white;
            color: var(--primary);
            transform: translateY(-3px);
        }

        .copyright {
            text-align: center;
            padding-top: 20px;
            border-top: 1px solid rgba(255, 255, 255, 0.2);
            color: rgba(255, 255, 255, 0.8);
            font-size: 0.9rem;
        }

        /* ===== Responsive Styles ===== */
        @media (max-width: 992px) {
            .hero-content {
                flex-direction: column-reverse;
                text-align: center;
            }
            
            .hero-text {
                max-width: 100%;
            }
            
            .hero-btns {
                justify-content: center;
            }
            
            .profile-photo {
                width: 300px;
                height: 300px;
                margin-bottom: 30px;
            }
            
            .about-content {
                grid-template-columns: 1fr;
            }
            
            .contact-container {
                grid-template-columns: 1fr;
            }
        }

        @media (max-width: 768px) {
            .menu-toggle {
                display: block;
            }
            
            .nav-links {
                position: fixed;
                top: 70px;
                left: -100%;
                width: 100%;
                height: calc(100vh - 70px);
                background: rgba(241, 245, 249, 0.98);
                flex-direction: column;
                align-items: center;
                padding-top: 50px;
                transition: var(--transition);
                backdrop-filter: blur(10px);
            }
            
            .nav-links.active {
                left: 0;
            }
            
            .nav-links li {
                margin: 15px 0;
            }
            
            .hero-text h1 {
                font-size: 2.5rem;
            }
            
            .section-title h2 {
                font-size: 2rem;
            }
            
            .projects-grid {
                grid-template-columns: 1fr;
            }
            
            .footer-content {
                flex-direction: column;
                gap: 20px;
            }
            
            .social-links {
                flex-direction: column;
                align-items: flex-start;
            }
        }

        @media (max-width: 576px) {
            .hero-text h1 {
                font-size: 2rem;
            }
            
            .hero-btns {
                flex-direction: column;
                align-items: center;
            }
          
