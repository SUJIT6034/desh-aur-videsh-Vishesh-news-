<!DOCTYPE html>
<html lang="hi">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>देश और विदेश का विशेष न्यूज</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }
        
        :root {
            --primary-color: #e63946;
            --secondary-color: #1d3557;
            --accent-color: #a8dadc;
            --light-color: #f1faee;
            --dark-color: #1d3557;
        }
        
        body {
            background-color: #f5f5f5;
            color: #333;
            line-height: 1.6;
        }
        
        .container {
            width: 100%;
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 15px;
        }
        
        /* Header Styles */
        header {
            background: linear-gradient(135deg, var(--secondary-color), var(--dark-color));
            color: white;
            padding: 15px 0;
            box-shadow: 0 4px 12px rgba(0, 0, 0, 0.1);
            position: sticky;
            top: 0;
            z-index: 1000;
        }
        
        .header-top {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 10px;
        }
        
        .logo {
            display: flex;
            align-items: center;
        }
        
        .logo h1 {
            font-size: 1.8rem;
            margin-left: 10px;
        }
        
        .logo-icon {
            font-size: 2.5rem;
            color: var(--primary-color);
        }
        
        .date-display {
            font-size: 1.1rem;
            background: rgba(255, 255, 255, 0.1);
            padding: 5px 15px;
            border-radius: 20px;
        }
        
        nav ul {
            display: flex;
            list-style: none;
            background: rgba(0, 0, 0, 0.2);
            border-radius: 5px;
            padding: 5px;
        }
        
        nav ul li {
            margin: 0 5px;
        }
        
        nav ul li a {
            color: white;
            text-decoration: none;
            padding: 8px 15px;
            border-radius: 5px;
            font-weight: 500;
            transition: all 0.3s ease;
        }
        
        nav ul li a:hover, 
        nav ul li a.active {
            background: var(--primary-color);
        }
        
        /* Hero Section */
        .hero {
            background: linear-gradient(rgba(29, 53, 87, 0.8), rgba(29, 53, 87, 0.9)), url('https://images.unsplash.com/photo-1588681664899-f142ff2dc9b1?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1074&q=80');
            background-size: cover;
            background-position: center;
            color: white;
            padding: 80px 0;
            text-align: center;
            margin-bottom: 40px;
        }
        
        .hero h2 {
            font-size: 2.8rem;
            margin-bottom: 20px;
            text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.5);
        }
        
        .hero p {
            font-size: 1.2rem;
            max-width: 800px;
            margin: 0 auto 30px;
        }
        
        .search-box {
            max-width: 600px;
            margin: 0 auto;
            position: relative;
        }
        
        .search-box input {
            width: 100%;
            padding: 15px 20px;
            border: none;
            border-radius: 50px;
            font-size: 1.1rem;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.2);
        }
        
        .search-box button {
            position: absolute;
            right: 5px;
            top: 5px;
            background: var(--primary-color);
            color: white;
            border: none;
            border-radius: 50px;
            padding: 10px 25px;
            font-size: 1rem;
            cursor: pointer;
            transition: all 0.3s ease;
        }
        
        .search-box button:hover {
            background: #c1121f;
        }
        
        /* News Section */
        .section-title {
            text-align: center;
            margin: 40px 0 30px;
            position: relative;
            color: var(--secondary-color);
        }
        
        .section-title::after {
            content: "";
            position: absolute;
            bottom: -10px;
            left: 50%;
            transform: translateX(-50%);
            width: 80px;
            height: 4px;
            background: var(--primary-color);
            border-radius: 2px;
        }
        
        .news-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
            gap: 30px;
            margin-bottom: 50px;
        }
        
        .news-card {
            background: white;
            border-radius: 10px;
            overflow: hidden;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
            transition: transform 0.3s ease, box-shadow 0.3s ease;
        }
        
        .news-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 15px 30px rgba(0, 0, 0, 0.15);
        }
        
        .card-image {
            height: 200px;
            overflow: hidden;
        }
        
        .card-image img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            transition: transform 0.5s ease;
        }
        
        .news-card:hover .card-image img {
            transform: scale(1.05);
        }
        
        .card-content {
            padding: 20px;
        }
        
        .news-category {
            display: inline-block;
            background: var(--primary-color);
            color: white;
            padding: 5px 12px;
            border-radius: 20px;
            font-size: 0.85rem;
            margin-bottom: 12px;
        }
        
        .card-content h3 {
            font-size: 1.4rem;
            margin-bottom: 12px;
            color: var(--dark-color);
        }
        
        .card-content p {
            color: #666;
            margin-bottom: 15px;
            font-size: 0.95rem;
        }
        
        .news-meta {
            display: flex;
            justify-content: space-between;
            color: #888;
            font-size: 0.9rem;
            border-top: 1px solid #eee;
            padding-top: 15px;
        }
        
        /* Video Section */
        .video-section {
            background: var(--light-color);
            padding: 50px 0;
            margin: 40px 0;
        }
        
        .video-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(320px, 1fr));
            gap: 25px;
        }
        
        .video-card {
            background: white;
            border-radius: 10px;
            overflow: hidden;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
        }
        
        .video-thumbnail {
            position: relative;
            height: 200px;
        }
        
        .video-thumbnail img {
            width: 100%;
            height: 100%;
            object-fit: cover;
        }
        
        .play-icon {
            position: absolute;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
            color: white;
            background: rgba(230, 57, 70, 0.8);
            width: 60px;
            height: 60px;
            border-radius: 50%;
            display: flex;
            justify-content: center;
            align-items: center;
            font-size: 1.5rem;
            cursor: pointer;
        }
        
        .video-info {
            padding: 20px;
        }
        
        .video-info h3 {
            margin-bottom: 10px;
            color: var(--dark-color);
        }
        
        /* Contact Section */
        .contact-section {
            background: linear-gradient(135deg, var(--secondary-color), var(--dark-color));
            color: white;
            padding: 60px 0;
            margin-top: 50px;
        }
        
        .contact-container {
            display: flex;
            flex-wrap: wrap;
            gap: 40px;
        }
        
        .contact-info {
            flex: 1;
            min-width: 300px;
        }
        
        .contact-info h2 {
            font-size: 2rem;
            margin-bottom: 20px;
            position: relative;
            padding-bottom: 15px;
        }
        
        .contact-info h2::after {
            content: "";
            position: absolute;
            bottom: 0;
            left: 0;
            width: 80px;
            height: 4px;
            background: var(--primary-color);
        }
        
        .contact-details {
            margin-top: 30px;
        }
        
        .contact-item {
            display: flex;
            align-items: flex-start;
            margin-bottom: 20px;
        }
        
        .contact-icon {
            font-size: 1.3rem;
            color: var(--accent-color);
            margin-right: 15px;
            margin-top: 5px;
        }
        
        .contact-form {
            flex: 1;
            min-width: 300px;
            background: rgba(255, 255, 255, 0.1);
            padding: 30px;
            border-radius: 10px;
        }
        
        .form-group {
            margin-bottom: 20px;
        }
        
        .form-group label {
            display: block;
            margin-bottom: 8px;
        }
        
        .form-group input,
        .form-group textarea {
            width: 100%;
            padding: 12px 15px;
            border: none;
            border-radius: 5px;
            background: rgba(255, 255, 255, 0.9);
            font-size: 1rem;
        }
        
        .form-group textarea {
            min-height: 120px;
            resize: vertical;
        }
        
        .submit-btn {
            background: var(--primary-color);
            color: white;
            border: none;
            padding: 12px 30px;
            border-radius: 5px;
            font-size: 1.1rem;
            cursor: pointer;
            transition: background 0.3s ease;
        }
        
        .submit-btn:hover {
            background: #c1121f;
        }
        
        /* Footer */
        footer {
            background: #1a1a2e;
            color: #ccc;
            padding: 40px 0 20px;
        }
        
        .footer-content {
            display: flex;
            flex-wrap: wrap;
            justify-content: space-between;
            gap: 40px;
            margin-bottom: 30px;
        }
        
        .footer-column {
            flex: 1;
            min-width: 200px;
        }
        
        .footer-column h3 {
            color: white;
            margin-bottom: 20px;
            position: relative;
            padding-bottom: 10px;
        }
        
        .footer-column h3::after {
            content: "";
            position: absolute;
            bottom: 0;
            left: 0;
            width: 40px;
            height: 3px;
            background: var(--primary-color);
        }
        
        .footer-column ul {
            list-style: none;
        }
        
        .footer-column ul li {
            margin-bottom: 12px;
        }
        
        .footer-column ul li a {
            color: #aaa;
            text-decoration: none;
            transition: color 0.3s ease;
        }
        
        .footer-column ul li a:hover {
            color: var(--accent-color);
        }
        
        .social-icons {
            display: flex;
            gap: 15px;
            margin-top: 20px;
        }
        
        .social-icon {
            display: flex;
            justify-content: center;
            align-items: center;
            width: 40px;
            height: 40px;
            background: rgba(255, 255, 255, 0.1);
            border-radius: 50%;
            color: white;
            text-decoration: none;
            transition: all 0.3s ease;
        }
        
        .social-icon:hover {
            background: var(--primary-color);
            transform: translateY(-5px);
        }
        
        .copyright {
            text-align: center;
            padding-top: 20px;
            border-top: 1px solid rgba(255, 255, 255, 0.1);
            font-size: 0.9rem;
        }
        
        /* Responsive Design */
        @media (max-width: 768px) {
            .header-top {
                flex-direction: column;
                text-align: center;
            }
            
            .date-display {
                margin-top: 10px;
            }
            
            nav ul {
                flex-wrap: wrap;
                justify-content: center;
            }
            
            .hero {
                padding: 50px 0;
            }
            
            .hero h2 {
                font-size: 2rem;
            }
        }
        
        @media (max-width: 480px) {
            .logo h1 {
                font-size: 1.5rem;
            }
            
            .hero h2 {
                font-size: 1.8rem;
            }
            
            .section-title {
                font-size: 1.8rem;
            }
        }
    </style>
</head>
<body>
    <!-- Header Section -->
    <header>
        <div class="container">
            <div class="header-top">
                <div class="logo">
                    <i class="fas fa-globe-asia logo-icon"></i>
                    <h1>देश और विदेश का विशेष न्यूज</h1>
                </div>
                <div class="date-display">
                    <i class="fas fa-calendar-alt"></i> 8 जुलाई 2025, मंगलवार
                </div>
            </div>
            
            <nav>
                <ul>
                    <li><a href="#" class="active">होम</a></li>
                    <li><a href="#">राजनीति</a></li>
                    <li><a href="#">व्यापार</a></li>
                    <li><a href="#">खेल</a></li>
                    <li><a href="#">मनोरंजन</a></li>
                    <li><a href="#">विज्ञान</a></li>
                    <li><a href="#">स्वास्थ्य</a></li>
                    <li><a href="#">वीडियो</a></li>
                </ul>
            </nav>
        </div>
    </header>

    <!-- Hero Section -->
    <section class="hero">
        <div class="container">
            <h2>विश्व भर से ताज़ा खबरें</h2>
            <p>देश और विदेश की सबसे विश्वसनीय और तेज खबरें, विश्लेषण और अपडेट्स। हमारे ऑटोमेटेड सिस्टम द्वारा 24/7 अपडेटेड</p>
            
            <div class="search-box">
                <input type="text" placeholder="खोजें...">
                <button><i class="fas fa-search"></i> खोजें</button>
            </div>
        </div>
    </section>

    <!-- Main Content -->
    <div class="container">
        <h2 class="section-title">ताज़ा खबरें</h2>
        
        <div class="news-grid">
            <!-- News Card 1 -->
            <div class="news-card">
                <div class="card-image">
                    <img src="https://images.unsplash.com/photo-1586339949916-3e9457bef6d3?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1170&q=80" alt="News Image">
                </div>
                <div class="card-content">
                    <span class="news-category">राजनीति</span>
                    <h3>केंद्र सरकार ने घोषित की नई शिक्षा नीति, 2025 से लागू होगी</h3>
                    <p>मानव संसाधन विकास मंत्रालय ने आज नई शिक्षा नीति की घोषणा की जिसमें कई बड़े बदलाव शामिल हैं। नई नीति में विद्यार्थियों के सर्वांगीण विकास पर जोर दिया गया है...</p>
                    <div class="news-meta">
                        <span><i class="far fa-clock"></i> 2 घंटे पहले</span>
                        <span><i class="far fa-eye"></i> 1.2k</span>
                    </div>
                </div>
            </div>
            
            <!-- News Card 2 -->
            <div class="news-card">
                <div class="card-image">
                    <img src="https://images.unsplash.com/photo-1586773860418-d37222d8fce3?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1173&q=80" alt="News Image">
                </div>
                <div class="card-content">
                    <span class="news-category">विज्ञान</span>
                    <h3>भारतीय वैज्ञानिकों ने खोजा कैंसर का नया इलाज, सफलता दर 90%</h3>
                    <p>टाटा मेमोरियल अस्पताल के शोधकर्ताओं ने एक ऐसी थेरेपी विकसित की है जो कैंसर सेल्स को खत्म करने में अत्यधिक प्रभावी साबित हुई है। यह खोज विश्वभर में सुर्खियों में है...</p>
                    <div class="news-meta">
                        <span><i class="far fa-clock"></i> 4 घंटे पहले</span>
                        <span><i class="far fa-eye"></i> 2.4k</span>
                    </div>
                </div>
            </div>
            
            <!-- News Card 3 -->
            <div class="news-card">
                <div class="card-image">
                    <img src="https://images.unsplash.com/photo-1519671482749-fd09be7ccebf?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1170&q=80" alt="News Image">
                </div>
                <div class="card-content">
                    <span class="news-category">खेल</span>
                    <h3>भारत ने जीता एशिया कप 2025, पाकिस्तान को 5 विकटों से हराया</h3>
                    <p>कोलंबो में खेले गए फाइनल मुकाबले में भारतीय क्रिकेट टीम ने पाकिस्तान को 5 विकटों से हराकर एशिया कप पर कब्जा जमाया। विराट कोहली ने शानदार शतक जड़ा...</p>
                    <div class="news-meta">
                        <span><i class="far fa-clock"></i> 6 घंटे पहले</span>
                        <span><i class="far fa-eye"></i> 4.7k</span>
                    </div>
                </div>
            </div>
            
            <!-- News Card 4 -->
            <div class="news-card">
                <div class="card-image">
                    <img src="https://images.unsplash.com/photo-1588702547919-26089e270437?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1170&q=80" alt="News Image">
                </div>
                <div class="card-content">
                    <span class="news-category">व्यापार</span>
                    <h3>रुपया अमेरिकी डॉलर के मुकाबले मजबूत, एक्सचेंज रेट 76.20 पर पहुंचा</h3>
                    <p>विदेशी निवेश में बढ़ोतरी और निर्यात में वृद्धि के कारण भारतीय रुपया लगातार तीसरे दिन मजबूत हुआ है। विशेषज्ञों के अनुसार आने वाले दिनों में रुपया और मजबूत हो सकता है...</p>
                    <div class="news-meta">
                        <span><i class="far fa-clock"></i> 8 घंटे पहले</span>
                        <span><i class="far fa-eye"></i> 1.8k</span>
                    </div>
                </div>
            </div>
            
            <!-- News Card 5 -->
            <div class="news-card">
                <div class="card-image">
                    <img src="https://images.unsplash.com/photo-1593118247619-e2d6f056869e?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1170&q=80" alt="News Image">
                </div>
                <div class="card-content">
                    <span class="news-category">दुनिया</span>
                    <h3>यूरोप में भीषण गर्मी की लहर, तापमान ने तोड़ा 50 साल का रिकॉर्ड</h3>
                    <p>यूरोपीय देशों में जारी भीषण गर्मी की लहर के कारण कई जगहों पर तापमान ने 45 डिग्री सेल्सियस को पार कर लिया है। स्पेन और पुर्तगाल में स्थिति सबसे गंभीर है...</p>
                    <div class="news-meta">
                        <spa
