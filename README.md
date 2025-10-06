<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <!-- Font Awesome CDN for social/contact icons (v6.5.1) -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.1/css/all.min.css" crossorigin="anonymous" referrerpolicy="no-referrer" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Ragupathi - Portfolio</title>
    <style>
        /* Contact Details Custom Alignment */
        .contact-details {
            display: flex;
            flex-direction: column;
            gap: 18px;
            margin-top: 25px;
        }
        .contact-item {
            display: flex;
            align-items: center;
            gap: 12px;
            font-size: 17px;
            color: #00f5ff;
            background: rgba(0, 245, 255, 0.07);
            padding: 12px 18px;
            border-radius: 8px;
            font-weight: 500;
            width: fit-content;
            box-shadow: 0 2px 8px rgba(0,245,255,0.08);
            transition: background 0.2s;
        }
        .contact-item i {
            color: #00f5ff;
            font-size: 20px;
            min-width: 22px;
        }
        .contact-item span {
            color: #fff;
            font-size: 16px;
            letter-spacing: 0.2px;
        }
        .contact-item:hover {
            background: rgba(0, 245, 255, 0.15);
        }
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
            background: #0a0a0a;
            color: #fff;
            overflow-x: hidden;
        }

        /* Navigation Bar */
        nav {
            position: fixed;
            width: 100%;
            background: rgba(10, 10, 10, 0.95);
            padding: 20px 8%;
            display: flex;
            justify-content: space-between;
            align-items: center;
            z-index: 1000;
            backdrop-filter: blur(10px);
            transition: all 0.3s ease;
        }

        nav.scrolled {
            padding: 15px 8%;
            box-shadow: 0 5px 30px rgba(0, 245, 255, 0.3);
        }

        .logo {
            font-size: 32px;
            font-weight: bold;
            background: linear-gradient(135deg, #00f5ff, #0080ff);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            cursor: pointer;
            letter-spacing: 2px;
        }

        .nav-links {
            display: flex;
            list-style: none;
            gap: 35px;
        }

        .nav-links li a {
            color: #fff;
            text-decoration: none;
            font-size: 16px;
            font-weight: 500;
            transition: all 0.3s ease;
            position: relative;
            padding: 5px 0;
        }

        .nav-links li a::after {
            content: '';
            position: absolute;
            width: 0;
            height: 2px;
            background: linear-gradient(135deg, #00f5ff, #0080ff);
            bottom: 0;
            left: 0;
            transition: width 0.3s ease;
        }

        .nav-links li a:hover::after,
        .nav-links li a.active::after {
            width: 100%;
        }

        .nav-links li a:hover {
            color: #00f5ff;
        }

        .menu-toggle {
            display: none;
            flex-direction: column;
            cursor: pointer;
            z-index: 1001;
        }

        .menu-toggle span {
            width: 28px;
            height: 3px;
            background: #fff;
            margin: 4px 0;
            transition: all 0.3s ease;
            border-radius: 2px;
        }

        .menu-toggle.active span:nth-child(1) {
            transform: rotate(45deg) translate(8px, 8px);
        }

        .menu-toggle.active span:nth-child(2) {
            opacity: 0;
        }

        .menu-toggle.active span:nth-child(3) {
            transform: rotate(-45deg) translate(8px, -8px);
        }

        /* Home Section */
        #home {
            min-height: 100vh;
            display: flex;
            align-items: center;
            justify-content: center;
            padding: 120px 8% 80px;
            background: linear-gradient(135deg, #0a0a0a 0%, #1a1a2e 50%, #16213e 100%);
            position: relative;
            overflow: hidden;
        }

        #home::before {
            content: '';
            position: absolute;
            width: 500px;
            height: 500px;
            background: radial-gradient(circle, rgba(0,245,255,0.1) 0%, transparent 70%);
            top: -250px;
            right: -250px;
            animation: float 6s ease-in-out infinite;
        }

        #home::after {
            content: '';
            position: absolute;
            width: 400px;
            height: 400px;
            background: radial-gradient(circle, rgba(0,128,255,0.1) 0%, transparent 70%);
            bottom: -200px;
            left: -200px;
            animation: float 8s ease-in-out infinite;
        }

        @keyframes float {
            0%, 100% {
                transform: translateY(0);
            }
            50% {
                transform: translateY(-30px);
            }
        }

        .home-content {
            max-width: 700px;
            z-index: 1;
            animation: fadeInUp 1s ease;
        }

        @keyframes fadeInUp {
            from {
                opacity: 0;
                transform: translateY(50px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        .home-content h3 {
            font-size: 32px;
            color: #00f5ff;
            margin-bottom: 15px;
            font-weight: 600;
        }

        .home-content h1 {
            font-size: 64px;
            margin-bottom: 20px;
            background: linear-gradient(135deg, #fff, #00f5ff, #0080ff);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            line-height: 1.2;
        }

        .typing-text {
            font-size: 28px;
            color: #888;
            margin-bottom: 25px;
            min-height: 40px;
        }

        .typing-text span {
            color: #00f5ff;
            font-weight: 600;
        }

        .home-content p {
            font-size: 18px;
            line-height: 1.8;
            color: #ccc;
            margin-bottom: 35px;
        }

        .btn-group {
            display: flex;
            gap: 20px;
            flex-wrap: wrap;
        }

        .btn {
            display: inline-block;
            padding: 14px 35px;
            background: linear-gradient(135deg, #00f5ff, #0080ff);
            color: #fff;
            text-decoration: none;
            border-radius: 50px;
            font-weight: 600;
            font-size: 16px;
            transition: all 0.3s ease;
            box-shadow: 0 5px 20px rgba(0, 245, 255, 0.4);
            border: none;
            cursor: pointer;
        }

        .btn:hover {
            transform: translateY(-3px);
            box-shadow: 0 8px 30px rgba(0, 245, 255, 0.6);
        }

        .btn-outline {
            background: transparent;
            border: 2px solid #00f5ff;
            color: #00f5ff;
            box-shadow: none;
        }

        .btn-outline:hover {
            background: linear-gradient(135deg, #00f5ff, #0080ff);
            color: #fff;
            box-shadow: 0 8px 30px rgba(0, 245, 255, 0.6);
        }

        /* Section Styles */
        section {
            padding: 100px 8%;
            min-height: 100vh;
        }

        .section-title {
            text-align: center;
            font-size: 48px;
            margin-bottom: 70px;
            position: relative;
            font-weight: 700;
        }

        .section-title::after {
            content: '';
            position: absolute;
            width: 120px;
            height: 4px;
            background: linear-gradient(135deg, #00f5ff, #0080ff);
            bottom: -15px;
            left: 50%;
            transform: translateX(-50%);
            border-radius: 2px;
        }

        /* About Section */
        #about {
            background: #0f0f0f;
        }

        .about-content {
            display: grid;
            grid-template-columns: 1fr 1.5fr;
            gap: 60px;
            align-items: center;
            animation: fadeIn 1s ease;
        }

        @keyframes fadeIn {
            from {
                opacity: 0;
            }
            to {
                opacity: 1;
            }
        }

        .about-img {
            width: 100%;
            max-width: 350px;
            height: 350px;
            background: linear-gradient(135deg, #00f5ff, #0080ff);
            border-radius: 20px;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 120px;
            box-shadow: 0 10px 40px rgba(0, 245, 255, 0.3);
            transition: all 0.3s ease;
            margin: 0 auto;
        }

        .about-img:hover {
            transform: scale(1.05);
            box-shadow: 0 15px 50px rgba(0, 245, 255, 0.5);
        }

        .about-text h3 {
            font-size: 36px;
            color: #00f5ff;
            margin-bottom: 20px;
            font-weight: 700;
        }

        .about-text p {
            font-size: 18px;
            line-height: 1.8;
            color: #ccc;
            margin-bottom: 25px;
        }

        .about-info {
            display: grid;
            grid-template-columns: repeat(2, 1fr);
            gap: 20px;
            margin-top: 30px;
        }

        .about-info p {
            color: #888;
            font-size: 16px;
        }

        .about-info p span {
            color: #00f5ff;
            font-weight: 600;
            margin-right: 10px;
        }

        /* Skills Section */
        #skills {
            background: #0a0a0a;
        }

        .skills-container {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
            gap: 35px;
            max-width: 1200px;
            margin: 0 auto;
        }

        .skill-box {
            background: #1a1a2e;
            padding: 35px;
            border-radius: 15px;
            transition: all 0.3s ease;
            border: 1px solid transparent;
            position: relative;
            overflow: hidden;
        }

        .skill-box::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(0,245,255,0.1), transparent);
            transition: all 0.5s ease;
        }

        .skill-box:hover::before {
            left: 100%;
        }

        .skill-box:hover {
            transform: translateY(-10px);
            border-color: #00f5ff;
            box-shadow: 0 15px 40px rgba(0, 245, 255, 0.3);
        }

        .skill-icon {
            font-size: 48px;
            margin-bottom: 20px;
            background: linear-gradient(135deg, #00f5ff, #0080ff);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }

        .skill-box h3 {
            font-size: 24px;
            color: #00f5ff;
            margin-bottom: 15px;
            font-weight: 600;
        }

        .skill-box p {
            color: #ccc;
            margin-bottom: 20px;
            line-height: 1.6;
        }

        .skill-bar {
            background: #0a0a0a;
            height: 12px;
            border-radius: 10px;
            margin-top: 15px;
            overflow: hidden;
            position: relative;
        }

        .skill-progress {
            height: 100%;
            background: linear-gradient(90deg, #00f5ff, #0080ff);
            border-radius: 10px;
            position: relative;
            animation: progressAnimation 2s ease;
            box-shadow: 0 0 10px rgba(0,245,255,0.5);
        }

        .skill-progress::after {
            content: attr(data-progress);
            position: absolute;
            right: 10px;
            top: 50%;
            transform: translateY(-50%);
            color: #fff;
            font-size: 11px;
            font-weight: 600;
        }

        @keyframes progressAnimation {
            from {
                width: 0;
            }
        }

        /* Projects Section */
        #projects {
            background: #0f0f0f;
        }

        .projects-container {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(320px, 1fr));
            gap: 40px;
            max-width: 1200px;
            margin: 0 auto;
        }

        .project-card {
            background: #1a1a2e;
            border-radius: 15px;
            overflow: hidden;
            transition: all 0.3s ease;
            cursor: pointer;
            border: 1px solid transparent;
        }

        .project-card:hover {
            transform: translateY(-10px);
            border-color: #00f5ff;
            box-shadow: 0 20px 50px rgba(0, 245, 255, 0.3);
        }

        .project-img {
            width: 100%;
            height: 220px;
            background: linear-gradient(135deg, #1a1a2e, #16213e);
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 64px;
            position: relative;
            overflow: hidden;
        }

        .project-img::before {
            content: '';
            position: absolute;
            width: 100%;
            height: 100%;
            background: linear-gradient(135deg, rgba(0,245,255,0.2), rgba(0,128,255,0.2));
            opacity: 0;
            transition: all 0.3s ease;
        }

        .project-card:hover .project-img::before {
            opacity: 1;
        }

        .project-info {
            padding: 30px;
        }

        .project-info h3 {
            font-size: 24px;
            color: #00f5ff;
            margin-bottom: 12px;
            font-weight: 600;
        }

        .project-info p {
            color: #ccc;
            line-height: 1.7;
            margin-bottom: 20px;
            font-size: 15px;
        }

        .project-tags {
            display: flex;
            gap: 10px;
            flex-wrap: wrap;
        }

        .tag {
            padding: 6px 16px;
            background: rgba(0, 245, 255, 0.1);
            border: 1px solid #00f5ff;
            border-radius: 25px;
            font-size: 13px;
            color: #00f5ff;
            transition: all 0.3s ease;
        }

        .tag:hover {
            background: rgba(0, 245, 255, 0.2);
            transform: scale(1.05);
        }

        /* Education Section */
        #education {
            background: #0a0a0a;
        }

        .education-container {
            max-width: 900px;
            margin: 0 auto;
        }

        .education-item {
            background: #1a1a2e;
            padding: 35px;
            border-radius: 15px;
            margin-bottom: 30px;
            border-left: 4px solid #00f5ff;
            transition: all 0.3s ease;
            position: relative;
        }

        .education-item:hover {
            transform: translateX(10px);
            box-shadow: 0 10px 40px rgba(0, 245, 255, 0.3);
        }

        .education-item::before {
            content: '';
            position: absolute;
            left: -8px;
            top: 50%;
            transform: translateY(-50%);
            width: 16px;
            height: 16px;
            background: #00f5ff;
            border-radius: 50%;
            box-shadow: 0 0 15px rgba(0,245,255,0.8);
        }

        .education-header {
            display: flex;
            justify-content: space-between;
            align-items: start;
            margin-bottom: 15px;
            flex-wrap: wrap;
            gap: 15px;
        }

        .education-item h3 {
            font-size: 26px;
            color: #00f5ff;
            margin-bottom: 8px;
            font-weight: 600;
        }

        .education-item h4 {
            font-size: 20px;
            color: #ccc;
            font-weight: 500;
        }

        .education-date {
            background: linear-gradient(135deg, #e24d2c, #2d36a9);
            padding: 8px 18px;
            border-radius: 25px;
            font-size: 14px;
            font-weight: 600;
            color: #fff;
        }

        .education-item p {
            color: #aaa;
            line-height: 1.7;
            font-size: 16px;
        }

        /* Contact Section */
        #contact {
            background: #0f0f0f;
            min-height: auto;
        }

        .contact-container {
            max-width: 700px;
            margin: 0 auto;
        }

        .contact-info {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 25px;
            margin-bottom: 50px;
        }

        .contact-box {
            background: #1a1a2e;
            padding: 30px;
            border-radius: 15px;
            text-align: center;
            transition: all 0.3s ease;
            border: 1px solid transparent;
        }

        .contact-box:hover {
            border-color: #00f5ff;
            transform: translateY(-5px);
            box-shadow: 0 10px 30px rgba(0, 245, 255, 0.3);
        }

        .contact-icon {
            font-size: 40px;
            margin-bottom: 15px;
            background: linear-gradient(135deg, #00f5ff, #0080ff);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }

        .contact-box h3 {
            font-size: 20px;
            color: #00f5ff;
            margin-bottom: 10px;
            font-weight: 600;
        }

        .contact-box p {
            color: #ccc;
            font-size: 15px;
        }

        .contact-form {
            display: flex;
            flex-direction: column;
            gap: 25px;
        }

        .form-group {
            position: relative;
        }

        .form-group input,
        .form-group textarea {
            width: 100%;
            padding: 16px 20px;
            background: #1a1a2e;
            border: 2px solid transparent;
            border-radius: 10px;
            color: #fff;
            font-size: 16px;
            transition: all 0.3s ease;
            outline: none;
        }

        .form-group input:focus,
        .form-group textarea:focus {
            border-color: #00f5ff;
            box-shadow: 0 0 15px rgba(0, 245, 255, 0.3);
        }

        .form-group textarea {
            resize: vertical;
            min-height: 150px;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }

        .form-group input::placeholder,
        .form-group textarea::placeholder {
            color: #666;
        }

        .submit-btn {
            width: 100%;
            padding: 16px;
            background: linear-gradient(135deg, #00f5ff, #0080ff);
            color: #fff;
            border: none;
            border-radius: 10px;
            font-size: 18px;
            font-weight: 600;
            cursor: pointer;
            transition: all 0.3s ease;
            box-shadow: 0 5px 20px rgba(0, 245, 255, 0.4);
        }

        .submit-btn:hover {
            transform: translateY(-3px);
            box-shadow: 0 8px 30px rgba(0, 245, 255, 0.6);
        }

        /* Social Links */
        .social-links {
            display: flex;
            justify-content: center;
            gap: 20px;
            margin-top: 50px;
        }

        .social-links a {
