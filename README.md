<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Gudala Priyanka Sai Ramya | Full Stack Developer</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;500;600;700&family=Space+Grotesk:wght@400;500;600;700&display=swap');
        
        :root {
            --primary: #12b4eb;
            --secondary: #45b814;
        }
        
        html {scroll-behavior: smooth; scroll-padding-top: 5rem;}
        body {font-family: 'Poppins', sans-serif; background-color: #205386; color: #e1108e;}
        h1, h2, h3, h4, h5, h6 {font-family: 'Space Grotesk', sans-serif;}
        
        .text-gradient {
            background: linear-gradient(90deg, var(--primary), var(--secondary));
            -webkit-background-clip: text;
            background-clip: text;
            color: transparent;
        }
        
        .btn-primary {
            background: linear-gradient(90deg, var(--primary), #4f46e5);
            transition: all 0.3s ease;
        }
        
        .btn-primary:hover {transform: translateY(-3px); box-shadow: 0 10px 20px rgba(99, 102, 241, 0.3);}
        .card {transition: all 0.3s ease;}
        .card:hover {transform: translateY(-5px); box-shadow: 0 15px 30px rgba(0, 0, 0, 0.1);}
        
        .nav-link {position: relative;}
        .nav-link::after {
            content: '';
            position: absolute;
            bottom: -5px;
            left: 0;
            width: 0;
            height: 2px;
            background: var(--primary);
            transition: width 0.3s ease;
        }
        .nav-link:hover::after, .active::after {width: 100%;}
        
        .project-overlay {opacity: 0; transition: all 0.3s ease;}
        .project-card:hover .project-overlay {opacity: 1;}
        
        .timeline-item {position: relative;}
        .timeline-item::before {
            content: '';
            position: absolute;
            left: -38px;
            top: 0;
            width: 16px;
            height: 16px;
            border-radius: 50%;
            background: var(--primary);
            border: 3px solid white;
            z-index: 1;
        }
        .timeline-item::after {
            content: '';
            position: absolute;
            left: -31px;
            top: 16px;
            width: 2px;
            height: calc(100% + 20px);
            background: #e2e8f0;
        }
        .timeline-item:last-child::after {display: none;}
        
        .mobile-menu {
            transform: translateX(100%);
            transition: transform 0.3s ease-in-out;
        }
        .mobile-menu.open {transform: translateX(0);}
        
        .dark-mode {background-color: #0f172a; color: #e60ddb;}
        .dark-mode .card, .dark-mode .skill-pill {background-color: #1e293b; color: #097cef;}
        .dark-mode .text-gray-600, .dark-mode .text-gray-700 {color: #4b11eb;}
        .dark-mode .border-gray-200 {border-color: #334155;}
        .dark-mode .bg-white {background-color: #1e293b;}
        .dark-mode .text-gray-900 {color: #f8fafc;}
        
        .scroll-indicator {
            height: 3px;
            background: linear-gradient(90deg, var(--primary), var(--secondary));
            position: fixed;
            top: 0;
            left: 0;
            z-index: 9999;
            width: 0%;
        }
    </style>
</head>
<body>
    <!-- Scroll indicator -->
    <div class="scroll-indicator" id="scroll-indicator"></div>
    
    <!-- Header -->
    <header class="fixed top-0 left-0 w-full bg-white bg-opacity-90 backdrop-blur-sm z-50 shadow-sm transition-all duration-300" id="header">
        <div class="container mx-auto px-4 py-4 flex justify-between items-center">
            <a href="#myself" class="text-2xl font-bold text-gradient">ProtoFolio</a>
            
            <!-- Desktop Navigation -->
            <nav class="hidden md:flex space-x-8">
                <a href="#myself" class="nav-link active font-medium hover:text-indigo-600 transition-colors">Home</a>
                <a href="#about" class="nav-link font-medium hover:text-indigo-600 transition-colors">About</a>
                <a href="#skills" class="nav-link font-medium hover:text-indigo-600 transition-colors">Skills</a>
                <a href="#contact" class="nav-link font-medium hover:text-indigo-600 transition-colors">Contact</a>
            </nav>
            
            <!-- Theme Toggle -->
            <button id="theme-toggle" class="hidden md:flex items-center justify-center w-10 h-10 rounded-full bg-gray-100 hover:bg-gray-200 transition-colors">
                <i class="fas fa-moon text-gray-700"></i>
            </button>
            
            <!-- Mobile Menu Button -->
            <button id="mobile-menu-button" class="md:hidden flex items-center justify-center w-10 h-10 rounded-full bg-gray-100 hover:bg-gray-200 transition-colors">
                <i class="fas fa-bars text-gray-700"></i>
            </button>
        </div>
    </header>
    
    <!-- Mobile Menu -->
    <div id="mobile-menu" class="mobile-menu fixed top-0 right-0 h-full w-3/4 bg-white shadow-lg z-50 p-6">
        <div class="flex justify-end mb-8">
            <button id="close-menu" class="flex items-center justify-center w-10 h-10 rounded-full bg-gray-100 hover:bg-gray-200 transition-colors">
                <i class="fas fa-times text-gray-700"></i>
            </button>
        </div>
        <nav class="flex flex-col space-y-6">
            <a href="#myself" class="text-lg font-medium hover:text-indigo-600 transition-colors">Home</a>
            <a href="#about" class="text-lg font-medium hover:text-indigo-600 transition-colors">About</a>
            <a href="#skills" class="text-lg font-medium hover:text-indigo-600 transition-colors">Skills</a>
            <a href="#projects" class="text-lg font-medium hover:text-indigo-600 transition-colors">Projects</a>
            <a href="#experience" class="text-lg font-medium hover:text-indigo-600 transition-colors">Experience</a>
            <a href="#contact" class="text-lg font-medium hover:text-indigo-600 transition-colors">Contact</a>
        </nav>
        <div class="mt-8 pt-8 border-t border-gray-200">
            <button id="mobile-theme-toggle" class="flex items-center space-x-2 text-gray-700 hover:text-indigo-600 transition-colors">
                <i class="fas fa-moon"></i>
                <span>Toggle Dark Mode</span>
            </button>
        </div>
    </div>
    <section id="myself" class="min-h-screen flex items-center pt-20 pb-16">
        <div class="container mx-auto px-4">
            <div class="flex flex-col md:flex-row items-center">
                <div class="md:w-1/2 mb-10 md:mb-0">
                    <h1 class="text-4xl md:text-6xl font-bold mb-4">Hi, I'm <span class="text-gradient">Gudala Priyanka Sai Ramya</span></h1>
                    <h2 class="text-2xl md:text-3xl font-semibold mb-6">Full Stack Developer</h2>
                    <p class="text-gray-600 text-lg mb-8 max-w-lg">I craft beautiful, functional, and user-friendly web experiences with modern technologies and creative solutions.</p>
                    <div class="flex flex-wrap gap-4">
                        <a href="#contact" class="btn-primary text-white px-8 py-3 rounded-full font-medium">Get in Touch</a>
                        <a href="#projects" class="bg-white border-2 border-indigo-600 text-indigo-600 px-8 py-3 rounded-full font-medium hover:bg-indigo-50 transition-colors">View Projects</a>
                    </div>
                    <div class="flex mt-10 space-x-4">
                        <a href="https://github.com/ramyagudala" target="_blank" class="text-gray-600 hover:text-indigo-600 transition-colors">
                            <i class="fab fa-github text-2xl"></i>
                        </a>
                        <a href="https://www.linkedin.com/in/gudala-priyanka-sai-ramya-991538294/" target="_blank" class="text-gray-600 hover:text-indigo-600 transition-colors">
                            <i class="fab fa-linkedin text-2xl"></i>
                        </a>
                        <a href="https://www.instagram.com/__priya___16____/" target="_blank" class="text-gray-600 hover:text-indigo-600 transition-colors">
                            <i class="fab fa-instagram text-2xl"></i>
                        </a>
                    </div>
                </div>
                <div class="md:w-1/2 flex justify-center">
                    <div class="relative">
                        <div class="w-64 h-64 md:w-80 md:h-80 bg-indigo-600 rounded-full absolute -top-4 -left-4"></div>
                        <div class="w-64 h-64 md:w-80 md:h-80 bg-teal-500 rounded-full absolute -bottom-4 -right-4"></div>
                        <div class="w-64 h-64 md:w-80 md:h-80 bg-white rounded-full relative z-10 overflow-hidden border-8 border-white shadow-xl">
                            <svg viewBox="0 0 200 200" xmlns="http://www.w3.org/2000/svg" class="w-full h-full">
                                <path fill="#6366F1" d="M44.7,-76.4C58.8,-69.2,71.8,-59.1,79.6,-45.8C87.4,-32.6,90,-16.3,88.5,-1.5C87,13.4,81.3,26.8,73.6,38.7C65.9,50.6,56.1,61,44.1,67.3C32.1,73.5,16.1,75.7,0.7,74.6C-14.6,73.5,-29.3,69.2,-41.9,62.1C-54.5,55,-65.1,45.1,-71.8,33.1C-78.5,21.1,-81.3,7,-78.9,-6.4C-76.4,-19.8,-68.7,-32.6,-59.3,-43.9C-49.9,-55.3,-38.8,-65.2,-26.2,-73.5C-13.6,-81.8,0.5,-88.5,14.9,-87.1C29.3,-85.7,58.5,-76.2,44.7,-76.4Z" transform="translate(100 100)" />
                            </svg>
                            <div class="absolute inset-0 flex items-center justify-center">
                                <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 448 512" class="w-32 h-32 text-white">
                                    <path fill="currentColor" d="M224 256A128 128 0 1 0 224 0a128 128 0 1 0 0 256zm-45.7 48C79.8 304 0 383.8 0 482.3C0 498.7 13.3 512 29.7 512H418.3c16.4 0 29.7-13.3 29.7-29.7C448 383.8 368.2 304 269.7 304H178.3z"/>
                                </svg>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>
    <!-- About Section -->
    <section id="about" class="py-20 bg-gray-50">
        <div class="container mx-auto px-4">
            <div class="text-center mb-16">
                <h2 class="text-3xl md:text-4xl font-bold mb-4">About Me</h2>
                <div class="w-24 h-1 bg-indigo-600 mx-auto"></div>
            </div>
            <div class="flex flex-col md:flex-row items-center gap-10">
                <div class="md:w-1/2">
                    <div class="relative">
                        <div class="w-full h-96 bg-gray-200 rounded-lg overflow-hidden">
                            <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 1000 1000" class="w-full h-full">
                                <defs>
                                    <linearGradient id="grad" x1="0%" y1="0%" x2="100%" y2="100%">
                                        <stop offset="0%" style="stop-color:#6366f1;stop-opacity:1" />
                                        <stop offset="100%" style="stop-color:#14b8a6;stop-opacity:1" />
                                    </linearGradient>
                                </defs>
                                <path fill="url(#grad)" d="M0,500L40,466.7C80,433,160,367,240,350C320,333,400,367,480,400C560,433,640,467,720,450C800,433,880,367,920,333.3L960,300L960,0L920,0C880,0,800,0,720,0C640,0,560,0,480,0C400,0,320,0,240,0C160,0,80,0,40,0L0,0Z"></path>
                                <path fill="url(#grad)" opacity="0.5" d="M0,500L40,483.3C80,467,160,433,240,416.7C320,400,400,400,480,416.7C560,433,640,467,720,483.3C800,500,880,500,920,500L960,500L960,0L920,0C880,0,800,0,720,0C640,0,560,0,480,0C400,0,320,0,240,0C160,0,80,0,40,0L0,0Z"></path>
                            </svg>
                            <div class="absolute inset-0 flex items-center justify-center">
                                <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 640 512" class="w-40 h-40 text-white">
                                    <path fill="currentColor" d="M392.8 1.2c-17-4.9-34.7 5-39.6 22l-128 448c-4.9 17 5 34.7 22 39.6s34.7-5 39.6-22l128-448c4.9-17-5-34.7-22-39.6zm80.6 120.1c-12.5 12.5-12.5 32.8 0 45.3L562.7 256l-89.4 89.4c-12.5 12.5-12.5 32.8 0 45.3s32.8 12.5 45.3 0l112-112c12.5-12.5 12.5-32.8 0-45.3l-112-112c-12.5-12.5-32.8-12.5-45.3 0zm-306.7 0c-12.5-12.5-32.8-12.5-45.3 0l-112 112c-12.5 12.5-12.5 32.8 0 45.3l112 112c12.5 12.5 32.8 12.5 45.3 0s12.5-32.8 0-45.3L77.3 256l89.4-89.4c12.5-12.5 12.5-32.8 0-45.3z"/>
                                </svg>
                            </div>
                        </div>
                    </div>
                </div>
                <div class="md:w-1/2 mt-12 md:mt-0">
                    <h3 class="text-2xl font-bold mb-4">Full Stack developer</h3>
                    <p class="text-gray-600 mb-6">I am a passionate Full Stack Developer with a strong foundation in both front-end and back-end technologies. I specialize in building responsive, user-friendly web applications using modern frameworks like React, Node.js, and Express, along with databases such as MongoDB and MySQL.</p>
                    <p class="text-gray-600 mb-6">My journey into full stack development began with a curiosity for how websites work behind the scenes. Starting with front-end basics like HTML, CSS, and JavaScript.</p>
                    <div class="grid grid-cols-2 gap-4">
                        <div>
                            <h4 class="font-semibold text-lg mb-2">Location</h4>
                            <p class="text-gray-600">Hyderabad, India</p>
                        </div>
                        <div>
                            <h4 class="font-semibold text-lg mb-2">Email</h4>
                            <p class="text-gray-600">priyanka240624@gmail.com</p>
                        </div>
                        <div>
                            <h4 class="font-semibold text-lg mb-2">Education</h4>
                            <p class="text-gray-600">ECE (Electronics And Communication Engineering)</p>
                            <p class="text-gray-600 text-sm">2022 - 2026 (Pursuing)</p>
                        </div>
                        <div>
                            <h4 class="font-semibold text-lg mb-2">Phone</h4>
                            <p class="text-gray-600">+91 9502494345</p>
                        </div>
                    </div>
                    <div class="mt-8">
                        <a href="#" class="inline-flex items-center text-indigo-600 font-medium hover:text-indigo-700 transition-colors">
                            <span>Download Resume</span>
                            <i class="fas fa-download ml-2"></i>
                        </a>
                    </div>
                </div>
            </div>
        </div>
    </section>
    <!-- Skills Section -->
    <section id="skills" class="py-20">
        <div class="container mx-auto px-4">
            <div class="text-center mb-16">
                <h2 class="text-3xl md:text-4xl font-bold mb-4">My Skills</h2>
                <div class="w-24 h-1 bg-indigo-600 mx-auto"></div>
                <p class="text-gray-600 mt-4 max-w-2xl mx-auto">I've worked with a variety of technologies and frameworks to build complete and responsive web applications. </p>
            </div>
            
            <div class="grid grid-cols-1 md:grid-cols-2 gap-10">
                <div class="card bg-white rounded-xl shadow-lg p-8">
                    <div class="flex items-center mb-6">
                        <div class="w-12 h-12 bg-indigo-100 rounded-lg flex items-center justify-center mr-4">
                            <i class="fas fa-code text-indigo-600 text-xl"></i>
                        </div>
                        <h3 class="text-2xl font-bold">Full Stack Development</h3>
                    </div>
                    <div class="space-y-4">
                        <div class="skill-item">
                            <div class="flex justify-between mb-1">
                                <span class="font-medium">HTML/CSS</span>
                                <span>95%</span>
                            </div>
                            <div class="w-full bg-gray-200 rounded-full h-2">
                                <div class="bg-indigo-600 h-2 rounded-full" style="width: 95%;"></div>
                            </div>
                        </div>
                        <div class="skill-item">
                            <div class="flex justify-between mb-1">
                                <span class="font-medium">JavaScript</span>
                                <span>80%</span>
                            </div>
                            <div class="w-full bg-gray-200 rounded-full h-2">
                                <div class="bg-indigo-600 h-2 rounded-full" style="width: 90%;"></div>
                            </div>
                        </div>
                        <div class="skill-item">
                            <div class="flex justify-between mb-1">
                                <span class="font-medium">React</span>
                                <span>75%</span>
                            </div>
                            <div class="w-full bg-gray-200 rounded-full h-2">
                                <div class="bg-indigo-600 h-2 rounded-full" style="width: 85%;"></div>
                            </div>
                        </div>
                    </div>
                </div>
                <!-- Programming Languages -->
                <div class="card bg-white rounded-xl shadow-lg p-8">
                    <div class="flex items-center mb-6">
                        <div class="w-12 h-12 bg-teal-100 rounded-lg flex items-center justify-center mr-4">
                            <i class="fas fa-laptop-code text-teal-600 text-xl"></i>
                        </div>
                        <h3 class="text-2xl font-bold">Programming Languages</h3>
                    </div>
                    <div class="space-y-4">
                        <div class="skill-item">
                            <div class="flex justify-between mb-1">
                                <span class="font-medium">JavaScript</span>
                                <span>90%</span>
                            </div>
                            <div class="w-full bg-gray-200 rounded-full h-2">
                                <div class="bg-teal-600 h-2 rounded-full" style="width: 90%;"></div>
                            </div>
                        </div>
                        <div class="skill-item">
                            <div class="flex justify-between mb-1">
                                <span class="font-medium">Python</span>
                                <span>80%</span>
                            </div>
                            <div class="w-full bg-gray-200 rounded-full h-2">
                                <div class="bg-teal-600 h-2 rounded-full" style="width: 80%;"></div>
                            </div>
                        </div>
                        </div>
                    </div>
                </div>
            </div>
            
            <!-- Additional Skills -->
            <div class="mt-16">
                <h3 class="text-xl font-bold mb-6 text-center">Additional Technologies</h3>
                <div class="flex flex-wrap justify-center gap-3">
                    <span class="skill-pill bg-white px-4 py-2 rounded-full shadow-md text-gray-700">HTML</span>
                    <span class="skill-pill bg-white px-4 py-2 rounded-full shadow-md text-gray-700">CSS</span>
                    <span class="skill-pill bg-white px-4 py-2 rounded-full shadow-md text-gray-700">JavaScript</span>
                    <span class="skill-pill bg-white px-4 py-2 rounded-full shadow-md text-gray-700">Python</span>
                    <span class="skill-pill bg-white px-4 py-2 rounded-full shadow-md text-gray-700">React</span>
                </div>
            </div>
        </div>
    </section>
    <!-- Education -->
                <div class="md:w-1/2">
                    <h3 class="text-2xl font-bold mb-8 flex items-center">
                        <div class="w-10 h-10 bg-teal-100 rounded-lg flex items-center justify-center mr-3">
                            <i class="fas fa-graduation-cap text-teal-600"></i>
                        </div>
                        Education
                    </h3>
                    
                    <div class="relative pl-10 border-l-2 border-gray-200 ml-7">
                        <!-- Education 1 -->
                        <div class="timeline-item mb-12">
                            <div class="bg-white p-6 rounded-xl shadow-lg">
                                <div class="flex justify-between items-start mb-4">
                                    <div>
                                        <h4 class="text-xl font-bold">ECE(Electronics And Communication Engineering)</h4>
                                        <p class="text-teal-600 font-medium">University Name</p>
                                    </div>
                                    <span class="bg-teal-100 text-teal-700 text-xs px-3 py-1 rounded-full">2022 - 2026 (Pursuing)</span>
                                </div>
                                <p class="text-gray-600 mb-4">I have gained a strong foundation in electronic circuits, communication systems, signal processing, and embedded systems. Alongside core subjects, I’ve also developed an interest in software and web development, which has allowed me to combine my technical background with practical programming skills. </p>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>
    
    <!-- Contact Section -->
    <section id="contact" class="py-20 bg-gray-50">
        <div class="container mx-auto px-4">
            <div class="text-center mb-16">
                <h2 class="text-3xl md:text-4xl font-bold mb-4">Get In Touch</h2>
                <div class="w-24 h-1 bg-indigo-600 mx-auto"></div>
                <p class="text-gray-600 mt-4 max-w-2xl mx-auto">want to collaborate? Feel free to reach out!</p>
            </div>
            
            <div class="flex flex-col md:flex-row gap-10">
                <!-- Contact Information -->
                <div class="md:w-1/2">
                    <div class="bg-white rounded-xl shadow-lg p-8">
                        <h3 class="text-2xl font-bold mb-6">Contact Information</h3>
                        <div class="space-y-6">
                            <div class="flex items-start">
                                <div class="w-12 h-12 bg-indigo-100 rounded-lg flex items-center justify-center mr-4">
                                    <i class="fas fa-map-marker-alt text-indigo-600"></i>
                                </div>
                                <div>
                                    <h4 class="font-semibold text-lg">Location</h4>
                                    <p class="text-gray-600">Hyderabad, India</p>
                                </div>
                            </div>
                            <div class="flex items-start">
                                <div class="w-12 h-12 bg-indigo-100 rounded-lg flex items-center justify-center mr-4">
                                    <i class="fas fa-envelope text-indigo-600"></i>
                                </div>
                                <div>
                                    <h4 class="font-semibold text-lg">Email</h4>
                                    <a href="mailto:priyanka240624@gmail.com" class="text-gray-600 hover:text-indigo-600 transition-colors">priyanka240624@gmail.com</a>
                                </div>
                            </div>
                            <div class="flex items-start">
                                <div class="w-12 h-12 bg-indigo-100 rounded-lg flex items-center justify-center mr-4">
                                    <i class="fas fa-phone-alt text-indigo-600"></i>
                                </div>
                                <div>
                                    <h4 class="font-semibold text-lg">Phone</h4>
                                    <a href="tel:+919347049203" class="text-gray-600 hover:text-indigo-600 transition-colors">+91 9502494345</a>
                                </div>
                            </div>
                        </div>
                        
                        <div class="mt-8">
                            <h4 class="font-semibold text-lg mb-4">Follow Me</h4>
                            <div class="flex space-x-4">
                                <a href="https://github.com/ramyagudala" target="_blank" class="w-10 h-10 bg-gray-100 rounded-full flex items-center justify-center text-gray-600 hover:bg-indigo-600 hover:text-white transition-colors">
                                    <i class="fab fa-github"></i>
                                </a>
                                <a href="https://www.linkedin.com/in/gudala-priyanka-sai-ramya-991538294/" target="_blank" class="w-10 h-10 bg-gray-100 rounded-full flex items-center justify-center text-gray-600 hover:bg-indigo-600 hover:text-white transition-colors">
                                    <i class="fab fa-linkedin-in"></i>
                                </a>
                                <a href="https://www.instagram.com/__priya___16____/" target="_blank" class="w-10 h-10 bg-gray-100 rounded-full flex items-center justify-center text-gray-600 hover:bg-indigo-600 hover:text-white transition-colors">
                                    <i class="fab fa-instagram"></i>
                                </a>
                            </div>
                        </div>
                    </div>
                </div>
                
                <!-- Contact Form -->
                <div class="md:w-1/2">
                    <div class="bg-white rounded-xl shadow-lg p-8">
                        <h3 class="text-2xl font-bold mb-6">Send Me a Message</h3>
                        <form id="messageForm" class="space-y-4">
                            <div>
                                <label for="name" class="block text-gray-700 font-medium mb-2">Your Name</label>
                                <input type="text" id="name" name="name" class="w-full px-4 py-2 border border-gray-300 rounded-lg focus:outline-none focus:ring-2 focus:ring-indigo-500" required>
                            </div>
                            <div>
                                <label for="email" class="block text-gray-700 font-medium mb-2">Your Email</label>
                                <input type="email" id="email" name="email" class="w-full px-4 py-2 border border-gray-300 rounded-lg focus:outline-none focus:ring-2 focus:ring-indigo-500" required>
                            </div>
                            <div>
                                <label for="message" class="block text-gray-700 font-medium mb-2">Message</label>
                                <textarea id="message" name="message" rows="5" class="w-full px-4 py-2 border border-gray-300 rounded-lg focus:outline-none focus:ring-2 focus:ring-indigo-500" required></textarea>
                            </div>
                            <div>
                                <button type="submit" class="btn-primary text-white px-6 py-3 rounded-lg font-medium w-full">Send Message</button>
                            </div>
                        </form>
                        <div id="form-success" class="mt-4 p-4 bg-green-100 text-green-700 rounded-lg hidden">
                            Your message has been sent successfully! I'll get back to you soon.
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>
    
    <!-- Footer -->
    <footer class="bg-gray-900 text-white py-10">
        <div class="container mx-auto px-4">
            <div class="flex flex-col md:flex-row justify-between items-center">
                <div class="mb-6 md:mb-0">
                    <h2 class="text-2xl font-bold text-gradient mb-2">Gudala Priyanka Sai Ramya/h2>
                    <p class="text-gray-400">Full Stack Developer</p>
                </div>
                <div class="flex space-x-6">
                    <a href="https://github.com/ramyagudala" target="_blank" class="text-gray-400 hover:text-white transition-colors">
                        <i class="fab fa-github text-xl"></i>
                    </a>
                    <a href="https://www.linkedin.com/in/gudala-priyanka-sai-ramya-991538294/" target="_blank" class="text-gray-400 hover:text-white transition-colors">
                        <i class="fab fa-linkedin-in text-xl"></i>
                    </a>
                    <a href="https://www.instagram.com/__priya___16____/" target="_blank" class="text-gray-400 hover:text-white transition-colors">
                        <i class="fab fa-instagram text-xl"></i>
                    </a>
                </div>
            </div>
            <div class="border-t border-gray-800 mt-8 pt-8 text-center">
                <p class="text-gray-400 text-sm">&copy; 2022 Gudala Priyanka Sai Ramya. All rights reserved.</p>
            </div>
        </div>
    </footer>
    
    <!-- Back to top button -->
    <button id="back-to-top" class="fixed bottom-6 right-6 w-12 h-12 bg-indigo-600 text-white rounded-full flex items-center justify-center shadow-lg z-50 opacity-0 invisible transition-all duration-300">
        <i class="fas fa-arrow-up"></i>
    </button>
    
    <script>
        // Mobile menu functionality
        const mobileMenuButton = document.getElementById('mobile-menu-button');
        const closeMenuButton = document.getElementById('close-menu');
        const mobileMenu = document.getElementById('mobile-menu');
        
        mobileMenuButton.addEventListener('click', () => {
            mobileMenu.classList.add('open');
        });
        
        closeMenuButton.addEventListener('click', () => {
            mobileMenu.classList.remove('open');
        });
        
        // Close mobile menu when clicking on a link
        const mobileMenuLinks = mobileMenu.querySelectorAll('a');
        mobileMenuLinks.forEach(link => {
            link.addEventListener('click', () => {
                mobileMenu.classList.remove('open');
            });
        });
        
        // Theme toggle functionality
        const themeToggle = document.getElementById('theme-toggle');
        const mobileThemeToggle = document.getElementById('mobile-theme-toggle');
        const body = document.body;
        
        function toggleDarkMode() {
            body.classList.toggle('dark-mode');
            const isDarkMode = body.classList.contains('dark-mode');
            
            // Update toggle icons
            if (isDarkMode) {
                themeToggle.innerHTML = '<i class="fas fa-sun text-yellow-400"></i>';
                mobileThemeToggle.innerHTML = '<i class="fas fa-sun text-yellow-400"></i><span>Toggle Light Mode</span>';
            } else {
                themeToggle.innerHTML = '<i class="fas fa-moon text-gray-700"></i>';
                mobileThemeToggle.innerHTML = '<i class="fas fa-moon"></i><span>Toggle Dark Mode</span>';
            }
            
            // Save preference to localStorage
            localStorage.setItem('darkMode', isDarkMode);
        }
        
        themeToggle.addEventListener('click', toggleDarkMode);
        mobileThemeToggle.addEventListener('click', toggleDarkMode);
        
        // Check for saved theme preference
        const savedDarkMode = localStorage.getItem('darkMode') === 'true';
        if (savedDarkMode) {
            body.classList.add('dark-mode');
            themeToggle.innerHTML = '<i class="fas fa-sun text-yellow-400"></i>';
            mobileThemeToggle.innerHTML = '<i class="fas fa-sun text-yellow-400"></i><span>Toggle Light Mode</span>';
        }
        
        // Scroll indicator
        const scrollIndicator = document.getElementById('scroll-indicator');
        
        window.addEventListener('scroll', () => {
            const scrollHeight = document.documentElement.scrollHeight - window.innerHeight;
            const scrolled = (window.scrollY / scrollHeight) * 100;
            scrollIndicator.style.width = scrolled + '%';
        });
        
        // Back to top button
        const backToTopButton = document.getElementById('back-to-top');
        
        window.addEventListener('scroll', () => {
            if (window.scrollY > 300) {
                backToTopButton.classList.remove('opacity-0', 'invisible');
                backToTopButton.classList.add('opacity-100', 'visible');
            } else {
                backToTopButton.classList.add('opacity-0', 'invisible');
                backToTopButton.classList.remove('opacity-100', 'visible');
            }
        });
        
        backToTopButton.addEventListener('click', () => {
            window.scrollTo({
                top: 0,
                behavior: 'smooth'
            });
        });
        
        // Active navigation link
        const sections = document.querySelectorAll('section');
        const navLinks = document.querySelectorAll('.nav-link');
        
        window.addEventListener('scroll', () => {
            let current = '';
            
            sections.forEach(section => {
                const sectionTop = section.offsetTop - 100;
                const sectionHeight = section.clientHeight;
                
                if (window.scrollY >= sectionTop && window.scrollY < sectionTop + sectionHeight) {
                    current = section.getAttribute('id');
                }
            });
            
            navLinks.forEach(link => {
                link.classList.remove('active');
                if (link.getAttribute('href') === '#' + current) {
                    link.classList.add('active');
                }
            });
        });
        
        // Form submission
        const messageForm = document.getElementById('messageForm');
        const formSuccess = document.getElementById('form-success');
        
        if (messageForm) {
            messageForm.addEventListener('submit', (e) => {
                e.preventDefault();
                
                // Simulate form submission
                setTimeout(() => {
                    messageForm.reset();
                    formSuccess.classList.remove('hidden');
                    
                    setTimeout(() => {
                        formSuccess.classList.add('hidden');
                    }, 5000);
                }, 1000);
            });
        }
    </script>
</body>
</html>
