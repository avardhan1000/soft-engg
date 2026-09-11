<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">

    <title>SecureLife Insurance</title>

    <style>
        /* =========================
           RESET
        ========================= */

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        html {
            scroll-behavior: smooth;
        }

        body {
            font-family: Arial, Helvetica, sans-serif;
            background: #f4f7fc;
            color: #333;
            line-height: 1.6;
        }

        :root {
            --primary: #003366;
            --secondary: #00509d;
            --blue: #00a8ff;
            --light: #f4f7fc;
            --white: #ffffff;
            --green: #159447;
            --dark: #222;
            --gray: #666;
            --border: #d5d5d5;
        }

        section {
            padding: 70px 6%;
        }

        .section-title {
            text-align: center;
            color: var(--primary);
            font-size: 34px;
            margin-bottom: 12px;
        }

        .section-subtitle {
            text-align: center;
            color: var(--gray);
            margin-bottom: 40px;
        }

        button {
            font-family: inherit;
        }


        /* =========================
           HEADER
        ========================= */

        header {
            background: var(--primary);
            color: white;
            padding: 15px 6%;
            display: flex;
            align-items: center;
            justify-content: space-between;
            position: sticky;
            top: 0;
            z-index: 1000;
            box-shadow: 0 3px 15px rgba(0, 0, 0, 0.2);
        }

        .logo {
            font-size: 25px;
            font-weight: bold;
            white-space: nowrap;
        }

        .logo span {
            color: var(--blue);
        }

        nav {
            display: flex;
            align-items: center;
        }

        nav a {
            color: white;
            text-decoration: none;
            margin-left: 20px;
            font-weight: bold;
            transition: 0.3s;
        }

        nav a:hover {
            color: var(--blue);
        }

        .menu-btn {
            display: none;
            font-size: 28px;
            cursor: pointer;
        }


        /* =========================
           HERO
        ========================= */

        .hero {
            min-height: 570px;
            display: flex;
            align-items: center;
            justify-content: center;
            text-align: center;
            color: white;

            background:
                linear-gradient(
                    rgba(0, 51, 102, 0.93),
                    rgba(0, 80, 157, 0.9)
                );
        }

        .hero-content {
            max-width: 850px;
        }

        .hero h1 {
            font-size: 52px;
            margin-bottom: 18px;
        }

        .hero p {
            font-size: 20px;
            margin-bottom: 30px;
        }

        .hero-buttons {
            display: flex;
            justify-content: center;
            gap: 15px;
            flex-wrap: wrap;
        }

        .btn {
            padding: 14px 28px;
            border-radius: 7px;
            border: none;
            cursor: pointer;
            font-weight: bold;
            font-size: 15px;
            transition: 0.3s;
        }

        .primary-btn {
            background: white;
            color: var(--primary);
        }

        .primary-btn:hover {
            transform: translateY(-3px);
        }

        .secondary-btn {
            background: transparent;
            color: white;
            border: 2px solid white;
        }

        .secondary-btn:hover {
            background: white;
            color: var(--primary);
        }


        /* =========================
           STATS
        ========================= */

        .stats {
            margin-top: -55px;
            position: relative;
            padding-top: 0;
        }

        .stats-container {
            max-width: 1100px;
            margin: auto;
            background: white;
            padding: 30px;
            border-radius: 15px;
            display: grid;
            grid-template-columns: repeat(4, 1fr);
            gap: 20px;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.12);
        }

        .stat {
            text-align: center;
        }

        .stat h3 {
            color: var(--secondary);
            font-size: 30px;
        }

        .stat p {
            color: var(--gray);
        }


        /* =========================
           SEARCH
        ========================= */

        .search-box {
            max-width: 600px;
            margin: 0 auto 35px;
        }

        .search-box input {
            width: 100%;
            padding: 15px;
            border: 1px solid var(--border);
            border-radius: 8px;
            font-size: 16px;
            outline: none;
        }

        .search-box input:focus {
            border-color: var(--secondary);
        }


        /* =========================
           PLANS
        ========================= */

        .cards {
            max-width: 1150px;
            margin: auto;

            display: grid;
            grid-template-columns: repeat(3, 1fr);
            gap: 25px;
        }

        .card {
            background: white;
            padding: 30px;
            border-radius: 15px;
            box-shadow: 0 5px 20px rgba(0, 0, 0, 0.08);
            transition: 0.3s;
            position: relative;
            overflow: hidden;
        }

        .card:hover {
            transform: translateY(-8px);
            box-shadow: 0 15px 30px rgba(0, 0, 0, 0.15);
        }

        .card.popular {
            border: 2px solid var(--blue);
        }

        .badge {
            position: absolute;
            top: 16px;
            right: -38px;
            background: var(--blue);
            color: white;
            padding: 6px 40px;
            transform: rotate(45deg);
            font-size: 11px;
            font-weight: bold;
        }

        .card-icon {
            font-size: 45px;
            margin-bottom: 12px;
        }

        .card h3 {
            color: var(--primary);
            font-size: 23px;
            margin-bottom: 10px;
        }

        .card-description {
            color: var(--gray);
        }

        .price {
            color: var(--secondary);
            font-size: 28px;
            font-weight: bold;
            margin: 18px 0;
        }

        .price span {
            color: var(--gray);
            font-size: 14px;
            font-weight: normal;
        }

        .features {
            list-style: none;
            margin: 20px 0;
        }

        .features li {
            padding: 7px 0;
        }

        .features li::before {
            content: "✔ ";
            color: var(--green);
            font-weight: bold;
        }

        .plan-btn {
            width: 100%;
            padding: 13px;
            border: none;
            border-radius: 7px;
            background: var(--secondary);
            color: white;
            cursor: pointer;
            font-weight: bold;
        }

        .plan-btn:hover {
            background: var(--primary);
        }


        /* =========================
           CALCULATOR
        ========================= */

        .calculator {
            max-width: 850px;
            margin: auto;
            background: white;
            padding: 35px;
            border-radius: 15px;
            box-shadow: 0 5px 20px rgba(0, 0, 0, 0.1);
        }

        .form-grid {
            display: grid;
            grid-template-columns: repeat(2, 1fr);
            gap: 20px;
        }

        .form-group {
            width: 100%;
        }

        label {
            display: block;
            font-weight: bold;
            margin-bottom: 7px;
        }

        input,
        select,
        textarea {
            width: 100%;
            padding: 13px;
            border: 1px solid var(--border);
            border-radius: 7px;
            font-size: 15px;
            outline: none;
        }

        input:focus,
        select:focus,
        textarea:focus {
            border-color: var(--secondary);
        }

        .full-width {
            grid-column: 1 / -1;
        }

        .calculate-btn {
            width: 100%;
            padding: 14px;
            margin-top: 25px;
            background: var(--primary);
            color: white;
            border: none;
            border-radius: 7px;
            cursor: pointer;
            font-weight: bold;
            font-size: 16px;
        }

        .calculate-btn:hover {
            background: var(--secondary);
        }

        .result {
            display: none;
            margin-top: 25px;
            padding: 20px;
            background: #edf8ff;
            border-radius: 10px;
            text-align: center;
        }

        .result-title {
            color: var(--gray);
        }

        .result strong {
            display: block;
            color: var(--secondary);
            font-size: 30px;
            margin-top: 5px;
        }


        /* =========================
           PURCHASE FORM
        ========================= */

        .form-container {
            max-width: 850px;
            margin: auto;
            background: white;
            padding: 35px;
            border-radius: 15px;
            box-shadow: 0 5px 20px rgba(0, 0, 0, 0.1);
        }

        .submit-btn {
            width: 100%;
            padding: 14px;
            background: var(--primary);
            color: white;
            border: none;
            border-radius: 7px;
            cursor: pointer;
            margin-top: 20px;
            font-weight: bold;
            font-size: 16px;
        }

        .submit-btn:hover {
            background: var(--secondary);
        }

        #message {
            text-align: center;
            color: var(--green);
            font-weight: bold;
            margin-top: 15px;
        }


        /* =========================
           DASHBOARD
        ========================= */

        .dashboard {
            max-width: 1100px;
            margin: auto;

            display: grid;
            grid-template-columns: repeat(4, 1fr);
            gap: 20px;
        }

        .dashboard-card {
            background: white;
            padding: 25px;
            border-radius: 12px;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.08);
        }

        .dashboard-card h3 {
            color: var(--primary);
            margin-bottom: 12px;
        }

        .number {
            color: var(--secondary);
            font-size: 30px;
            font-weight: bold;
        }

        .status {
            display: inline-block;
            margin-top: 10px;
            padding: 5px 12px;
            border-radius: 20px;
            background: #dff7e8;
            color: var(--green);
            font-size: 13px;
        }


        /* =========================
           CLAIMS
        ========================= */

        .claim-box {
            max-width: 900px;
            margin: auto;
            background: white;
            padding: 35px;
            border-radius: 15px;
            box-shadow: 0 5px 20px rgba(0, 0, 0, 0.08);
        }

        .claim-intro {
            text-align: center;
            color: var(--gray);
        }

        .claim-steps {
            display: grid;
            grid-template-columns: repeat(3, 1fr);
            gap: 20px;
            margin: 30px 0;
        }

        .step {
            text-align: center;
            padding: 15px;
        }

        .step-number {
            display: flex;
            align-items: center;
            justify-content: center;

            width: 55px;
            height: 55px;

            margin: auto auto 12px;

            border-radius: 50%;
            background: var(--secondary);
            color: white;
            font-weight: bold;
            font-size: 20px;
        }

        .step h3 {
            color: var(--primary);
            margin-bottom: 5px;
        }

        .step p {
            color: var(--gray);
        }


        /* =========================
           TESTIMONIALS
        ========================= */

        .testimonials {
            max-width: 1100px;
            margin: auto;

            display: grid;
            grid-template-columns: repeat(3, 1fr);
            gap: 20px;
        }

        .testimonial {
            background: white;
            padding: 25px;
            border-radius: 12px;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.08);
        }

        .stars {
            color: #f5b301;
            font-size: 20px;
            margin-bottom: 10px;
        }

        .testimonial p {
            color: var(--gray);
        }

        .testimonial h4 {
            color: var(--primary);
            margin-top: 15px;
        }


        /* =========================
           FAQ
        ========================= */

        .faq {
            max-width: 850px;
            margin: auto;
        }

        .faq-item {
            background: white;
            margin-bottom: 12px;
            border-radius: 8px;
            overflow: hidden;
            box-shadow: 0 3px 10px rgba(0, 0, 0, 0.06);
        }

        .faq-question {
            padding: 18px;
            cursor: pointer;

            display: flex;
            justify-content: space-between;
            align-items: center;

            font-weight: bold;
            color: var(--primary);
        }

        .faq-icon {
            font-size: 20px;
        }

        .faq-answer {
            display: none;
            padding: 0 18px 18px;
            color: var(--gray);
        }

        .faq-item.active .faq-answer {
            display: block;
        }


        /* =========================
           CONTACT
        ========================= */

        .contact-info {
            max-width: 1000px;
            margin: auto;

            display: grid;
            grid-template-columns: repeat(3, 1fr);
            gap: 20px;
        }

        .contact-card {
            background: white;
            padding: 25px;
            text-align: center;
            border-radius: 12px;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.08);
        }

        .contact-card .icon {
            font-size: 35px;
            margin-bottom: 10px;
        }

        .contact-card h3 {
            color: var(--primary);
            margin-bottom: 8px;
        }

        .contact-card p {
            color: var(--gray);
        }


        /* =========================
           FOOTER
        ========================= */

        footer {
            background: var(--primary);
            color: white;
            text-align: center;
            padding: 40px 20px;
        }

        .footer-links {
            margin: 20px 0;
        }

        .footer-links a {
            color: white;
            text-decoration: none;
            margin: 0 10px;
        }

        .footer-links a:hover {
            color: var(--blue);
        }


        /* =========================
           BACK TO TOP
        ========================= */

        #topBtn {
            display: none;

            position: fixed;
            right: 20px;
            bottom: 20px;

            width: 48px;
            height: 48px;

            border: none;
            border-radius: 50%;

            background: var(--primary);
            color: white;

            font-size: 20px;
            cursor: pointer;

            z-index: 999;
            box-shadow: 0 3px 10px rgba(0, 0, 0, 0.2);
        }

        #topBtn:hover {
            background: var(--secondary);
        }


        /* =========================
           TOAST
        ========================= */

        #toast {
            position: fixed;
            left: 50%;
            bottom: 25px;

            transform: translateX(-50%);

            background: #222;
            color: white;

            padding: 13px 25px;
            border-radius: 8px;

            display: none;
            z-index: 2000;

            max-width: 90%;
            text-align: center;
        }


        /* =========================
           RESPONSIVE - TABLET
        ========================= */

        @media (max-width: 1000px) {

            .cards {
                grid-template-columns: repeat(2, 1fr);
            }

            .dashboard {
                grid-template-columns: repeat(2, 1fr);
            }

            .testimonials {
                grid-template-columns: repeat(2, 1fr);
            }

            .contact-info {
                grid-template-columns: repeat(2, 1fr);
            }

            .stats-container {
                grid-template-columns: repeat(2, 1fr);
            }
        }


        /* =========================
           RESPONSIVE - MOBILE
        ========================= */

        @media (max-width: 768px) {

            header {
                padding: 15px 20px;
            }

            .menu-btn {
                display: block;
            }

            nav {
                display: none;

                position: absolute;
                top: 65px;
                left: 0;

                width: 100%;

                background: var(--primary);

                flex-direction: column;

                padding: 15px 0;

                box-shadow: 0 5px 10px rgba(0, 0, 0, 0.2);
            }

            nav.active {
                display: flex;
            }

            nav a {
                margin: 12px 0;
            }

            section {
                padding: 55px 20px;
            }

            .hero {
                min-height: 500px;
            }

            .hero h1 {
                font-size: 36px;
            }

            .hero p {
                font-size: 17px;
            }

            .cards {
                grid-template-columns: 1fr;
            }

            .dashboard {
                grid-template-columns: 1fr;
            }

            .testimonials {
                grid-template-columns: 1fr;
            }

            .contact-info {
                grid-template-columns: 1fr;
            }

            .form-grid {
                grid-template-columns: 1fr;
            }

            .claim-steps {
                grid-template-columns: 1fr;
            }

            .full-width {
                grid-column: auto;
            }

            .calculator,
            .form-container,
            .claim-box {
                padding: 25px;
            }

            .stats {
                margin-top: -30px;
            }
        }


        /* =========================
           RESPONSIVE - SMALL MOBILE
        ========================= */

        @media (max-width: 480px) {

            .logo {
                font-size: 20px;
            }

            .hero h1 {
                font-size: 30px;
            }

            .section-title {
                font-size: 27px;
            }

            .hero-buttons {
                flex-direction: column;
            }

            .hero-buttons .btn {
                width: 100%;
            }

            .stats-container {
                grid-template-columns: 1fr;
            }

            .calculator,
            .form-container,
            .claim-box {
                padding: 20px;
            }
        }

    </style>
</head>


<body>


    <!-- ================= HEADER ================= -->

    <header>

        <div class="logo">
            Secure<span>Life</span>
    
