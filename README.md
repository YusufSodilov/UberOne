<!DOCTYPE html>
<html lang="ru">
<head>
    <base target="_self">
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>UberOne - Платформа для путешествий по Узбекистану</title>
    <meta name="description" content="UberOne — удобная онлайн-платформа для бронирования отелей и организации путешествий по Узбекистану с поддержкой трёх языков и AI-гидом">
    <script src="https://cdn.tailwindcss.com"></script>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/5.15.3/css/all.min.css">
    <script>
        tailwind.config = {
            theme: {
                extend: {
                    colors: {
                        primary: "#1e40af",
                        secondary: "#3b82f6",
                        accent: "#f59e0b",
                        dark: "#1f2937",
                        light: "#f8fafc",
                        uzbekblue: "#0099b5",
                        uzbekgreen: "#43b02a",
                        uzbekred: "#ce1126"
                    },
                    fontFamily: {
                        sans: ['Inter', 'system-ui', 'sans-serif'],
                    },
                    boxShadow: {
                        'premium': '0 20px 25px -5px rgba(0, 0, 0, 0.3), 0 10px 10px -5px rgba(0, 0, 0, 0.2)',
                    }
                }
            }
        }
    </script>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700&display=swap" rel="stylesheet">
</head>
<body class="font-sans bg-light text-dark min-h-screen flex flex-col">
    <!-- Header with Navigation -->
    <header class="bg-white shadow-lg sticky top-0 z-50">
        <nav class="container mx-auto px-4 py-4">
            <div class="flex justify-between items-center">
                <div class="flex items-center">
                    <h1 class="text-2xl font-bold text-primary">Uber<span class="text-accent">One</span></h1>
                </div>
                
                <div class="hidden md:flex space-x-8">
                    <a href="#hotels" class="text-dark hover:text-primary transition-colors">Отели</a>
                    <a href="#attractions" class="text-dark hover:text-primary transition-colors">Достопримечательности</a>
                    <a href="#tours" class="text-dark hover:text-primary transition-colors">Экскурсии</a>
                    <a href="#ai-guide" class="text-dark hover:text-primary transition-colors">AI-Гид</a>
                    <a href="#virtual-tour" class="text-dark hover:text-primary transition-colors">3D Тур</a>
                </div>
                
                <div class="flex items-center space-x-4">
                    <div class="hidden md:block">
                        <select id="language-select" class="bg-transparent border-none text-dark focus:outline-none">
                            <option value="ru">Русский</option>
                            <option value="uz">O'zbek</option>
                            <option value="en">English</option>
                        </select>
                    </div>
                    <button id="login-btn" class="bg-primary text-white px-6 py-2 rounded-lg hover:bg-secondary transition-colors">
                        Войти
                    </button>
                    <button class="md:hidden" id="mobile-menu-btn">
                        <i class="fas fa-bars text-2xl text-dark"></i>
                    </button>
                </div>
            </div>
        </nav>
    </header>

    <!-- Hero Section -->
    <section class="relative bg-gradient-to-r from-primary to-secondary text-white py-20">
        <div class="container mx-auto px-4">
            <div class="max-w-4xl mx-auto text-center">
                <h2 class="text-4xl md:text-5xl font-bold mb-6">Откройте Узбекистан с UberOne</h2>
                <p class="text-xl mb-8">Мост между культурой и технологией — ваш личный опыт путешествия</p>
                <div class="flex flex-col sm:flex-row gap-4 justify-center">
                    <button id="start-planning" class="bg-accent text-dark px-8 py-3 rounded-lg font-semibold hover:bg-yellow-500 transition-colors">
                        Начать планирование
                    </button>
                    <button id="download-app" class="bg-white text-primary px-8 py-3 rounded-lg font-semibold hover:bg-gray-100 transition-colors">
                        Скачать приложение
                    </button>
                </div>
            </div>
        </div>
    </section>

    <!-- Features Section with Black Background and Shadow -->
    <section class="py-16 bg-black text-white">
        <div class="container mx-auto px-4">
            <h2 class="text-3xl font-bold text-center mb-12">Наши преимущества</h2>
            <div class="grid md:grid-cols-2 lg:grid-cols-3 gap-8">
                <div class="text-center p-6 bg-gray-900 rounded-lg shadow-premium hover:shadow-xl transition-shadow">
                    <div class="w-16 h-16 bg-primary rounded-full flex items-center justify-center mx-auto mb-4">
                        <i class="fas fa-hotel text-2xl text-white"></i>
                    </div>
                    <h3 class="text-xl font-semibold mb-3">Бронирование отелей</h3>
                    <p class="text-gray-300">Забронируйте отель прямо через сайт с фильтрацией по цене и рейтингу</p>
                </div>
                
                <div class="text-center p-6 bg-gray-900 rounded-lg shadow-premium hover:shadow-xl transition-shadow">
                    <div class="w-16 h-16 bg-secondary rounded-full flex items-center justify-center mx-auto mb-4">
                        <i class="fas fa-globe text-2xl text-white"></i>
                    </div>
                    <h3 class="text-xl font-semibold mb-3">3 языка</h3>
                    <p class="text-gray-300">Поддержка узбекского, русского и английского языков</p>
                </div>
                
                <div class="text-center p-6 bg-gray-900 rounded-lg shadow-premium hover:shadow-xl transition-shadow">
                    <div class="w-16 h-16 bg-accent rounded-full flex items-center justify-center mx-auto mb-4">
                        <i class="fas fa-mobile-alt text-2xl text-white"></i>
                    </div>
                    <h3 class="text-xl font-semibold mb-3">Мобильное приложение</h3>
                    <p class="text-gray-300">Быстрый доступ ко всем функциям через мобильное приложение</p>
                </div>
                
                <div class="text-center p-6 bg-gray-900 rounded-lg shadow-premium hover:shadow-xl transition-shadow">
                    <div class="w-16 h-16 bg-primary rounded-full flex items-center justify-center mx-auto mb-4">
                        <i class="fas fa-headset text-2xl text-white"></i>
                    </div>
                    <h3 class="text-xl font-semibold mb-3">Поддержка 24/7</h3>
                    <p class="text-gray-300">Круглосуточная поддержка для решения любых вопросов</p>
                </div>
                
                <div class="text-center p-6 bg-gray-900 rounded-lg shadow-premium hover:shadow-xl transition-shadow">
                    <div class="w-16 h-16 bg-secondary rounded-full flex items-center justify-center mx-auto mb-4">
                        <i class="fas fa-handshake text-2xl text-white"></i>
                    </div>
                    <h3 class="text-xl font-semibold mb-3">Партнёрства</h3>
                    <p class="text-gray-300">Сотрудничество с отелями, авиакомпаниями и туроператорами</p>
                </div>
                
                <div class="text-center p-6 bg-gray-900 rounded-lg shadow-premium hover:shadow-xl transition-shadow">
                    <div class="w-16 h-16 bg-accent rounded-full flex items-center justify-center mx-auto mb-4">
                        <i class="fas fa-robot text-2xl text-white"></i>
                    </div>
                    <h3 class="text-xl font-semibold mb-3">AI-Гид</h3>
                    <p class="text-gray-300">Чат-бот поможет спланировать маршрут по вашим интересам</p>
                </div>
            </div>
        </div>
    </section>

    <!-- Attractions Section with Real Uzbek Landmarks -->
    <section id="attractions" class="py-16 bg-gray-50">
        <div class="container mx-auto px-4">
            <h2 class="text-3xl font-bold text-center mb-12">Достопримечательности Узбекистана</h2>
            <div class="grid md:grid-cols-2 lg:grid-cols-4 gap-6">
                <div class="bg-white rounded-lg overflow-hidden shadow-md hover:shadow-lg transition-shadow">
                    <img src="https://upload.wikimedia.org/wikipedia/commons/0/00/Registan_square_Samarkand.jpg?uselang=ru" alt="Регистан, Самарканд" class="w-full h-48 object-cover" loading="lazy">
                    <div class="p-4">
                        <h3 class="font-semibold text-lg mb-2">Регистан</h3>
                        <p class="text-gray-600 mb-3">Сердце древнего Самарканда с тремя величественными медресе</p>
                        <button class="attraction-btn text-primary hover:text-secondary transition-colors" data-id="1">
                            Подробнее
                        </button>
                    </div>
                </div>
                
                <div class="bg-white rounded-lg overflow-hidden shadow-md hover:shadow-lg transition-shadow">
                    <img src="https://upload.wikimedia.org/wikipedia/commons/e/e3/Samarkanda_IGP2772.jpg" alt="Мавзолей Гур-Эмир" class="w-full h-48 object-cover" loading="lazy">
                    <div class="p-4">
                        <h3 class="font-semibold text-lg mb-2">Гур-Эмир</h3>
                        <p class="text-gray-600 mb-3">Усыпальница Тамерлана и его потомков в Самарканде</p>
                        <button class="attraction-btn text-primary hover:text-secondary transition-colors" data-id="2">
                            Подробнее
                        </button>
                    </div>
                </div>
                
                <div class="bg-white rounded-lg overflow-hidden shadow-md hover:shadow-lg transition-shadow">
                    <img src="https://upload.wikimedia.org/wikipedia/commons/7/74/Shah-i-Zinda_%288145369659%29.jpg" alt="Шахи-Зинда" class="w-full h-48 object-cover" loading="lazy">
                    <div class="p-4">
                        <h3 class="font-semibold text-lg mb-2">Шахи-Зинда</h3>
                        <p class="text-gray-600 mb-3">Некрополь с мавзолеями знати времен Тамерлана</p>
                        <button class="attraction-btn text-primary hover:text-secondary transition-colors" data-id="3">
                            Подробнее
                        </button>
                    </div>
                </div>
                
                <div class="bg-white rounded-lg overflow-hidden shadow-md hover:shadow-lg transition-shadow">
                    <img src="https://upload.wikimedia.org/wikipedia/commons/9/92/Poi_Kalon.jpg" alt="Пои-Калян" class="w-full h-48 object-cover" loading="lazy">
                    <div class="p-4">
                        <h3 class="font-semibold text-lg mb-2">Пои-Калян</h3>
                        <p class="text-gray-600 mb-3">Архитектурный ансамбль в Бухаре с минаретом XII века</p>
                        <button class="attraction-btn text-primary hover:text-secondary transition-colors" data-id="4">
                            Подробнее
                        </button>
                    </div>
                </div>
            </div>
            
            <div class="text-center mt-8">
                <button id="view-all-attractions" class="bg-primary text-white px-8 py-3 rounded-lg font-semibold hover:bg-secondary transition-colors">
                    Смотреть все достопримечательности
                </button>
            </div>
        </div>
    </section>

    <!-- Exclusive Feature: Virtual 3D Tour -->
    <section id="virtual-tour" class="py-16 bg-gradient-to-r from-uzbekblue to-uzbekgreen text-white">
        <div class="container mx-auto px-4">
            <div class="text-center mb-12">
                <span class="bg-white text-uzbekblue px-4 py-1 rounded-full text-sm font-semibold">ЭКСКЛЮЗИВ</span>
                <h2 class="text-3xl font-bold mt-4">Виртуальный 3D Тур по Узбекистану</h2>
                <p class="text-xl mt-2">Только у нас — уникальная возможность исследовать достопримечательности в 3D</p>
            </div>
            
            <div class="grid md:grid-cols-2 gap-8 items-center">
                <div>
                    <div class="bg-black bg-opacity-30 rounded-2xl p-6 shadow-premium">
                        <h3 class="text-2xl font-semibold mb-4">Погрузитесь в историю с технологией VR</h3>
                        <ul class="space-y-3 mb-6">
                            <li class="flex items-center">
                                <i class="fas fa-vr-cardboard text-accent mr-3 text-xl"></i>
                                <span>Панорамные 360° туры по историческим местам</span>
                            </li>
                            <li class="flex items-center">
                                <i class="fas fa-history text-accent mr-3 text-xl"></i>
                                <span>Реконструкция древних сооружений в их первоначальном виде</span>
                            </li>
                            <li class="flex items-center">
                                <i class="fas fa-volume-up text-accent mr-3 text-xl"></i>
                                <span>Аудиогиды на трех языках с историческими справками</span>
                            </li>
                            <li class="flex items-center">
                                <i class="fas fa-mobile-alt text-accent mr-3 text-xl"></i>
                                <span>Совместимость с VR-очками и мобильными устройствами</span>
                            </li>
                        </ul>
                        <button id="start-vr-tour" class="bg-accent text-dark px-8 py-3 rounded-lg font-semibold hover:bg-yellow-500 transition-colors w-full">
                            Начать 3D Тур
                        </button>
                    </div>
                </div>
                
                <div class="relative">
                    <div class="bg-white bg-opacity-10 rounded-2xl p-2">
                        <img src="https://upload.wikimedia.org/wikipedia/commons/0/00/Registan_square_Samarkand.jpg" alt="3D Тур по Регистану" class="w-full rounded-xl shadow-lg">
                    </div>
                    <div class="absolute top-4 right-4 bg-accent text-dark px-3 py-1 rounded-full text-sm font-semibold">
                        3D Просмотр
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Booking Section -->
    <section id="hotels" class="py-16 bg-white">
        <div class="container mx-auto px-4">
            <h2 class="text-3xl font-bold text-center mb-12">Бронирование отелей</h2>
            <div class="bg-primary rounded-2xl p-8 text-white">
                <div class="grid md:grid-cols-4 gap-4">
                    <div>
                        <label class="block mb-2">Город</label>
                        <input type="text" placeholder="Куда едете?" class="w-full p-3 rounded-lg text-dark" id="destination-input">
                    </div>
                    <div>
                        <label class="block mb-2">Заезд</label>
                        <input type="date" class="w-full p-3 rounded-lg text-dark" id="checkin-date">
                    </div>
                    <div>
                        <label class="block mb-2">Выезд</label>
                        <input type="date" class="w-full p-3 rounded-lg text-dark" id="checkout-date">
                    </div>
                    <div>
                        <label class="block mb-2">Гости</label>
                        <div class="flex items-center bg-white rounded-lg">
                            <input type="number" value="2" class="w-full p-3 rounded-lg text-dark" id="guests-input">
                            <button class="px-3 text-dark">
                                <i class="fas fa-user"></i>
                            </button>
                        </div>
                    </div>
                </div>
                <button id="search-hotels" class="w-full bg-accent text-dark font-semibold py-3 rounded-lg mt-6 hover:bg-yellow-500 transition-colors">
                    Найти отели
                </button>
            </div>
        </div>
    </section>

    <!-- AI Guide Section -->
    <section id="ai-guide" class="py-16 bg-gray-50">
        <div class="container mx-auto px-4">
            <div class="grid md:grid-cols-2 gap-12 items-center">
                <div>
                    <h2 class="text-3xl font-bold mb-6">🤖 AI-Гид для вашего путешествия</h2>
                    <p class="text-lg mb-6">Наш интеллектуальный помощник подскажет, что посмотреть и куда отправиться, учитывая ваши интересы и предпочтения.</p>
                    <ul class="space-y-3 mb-8">
                        <li class="flex items-center">
                            <i class="fas fa-check-circle text-primary mr-3"></i>
                            <span>Персональные рекомендации</span>
                        </li>
                        <li class="flex items-center">
                            <i class="fas fa-check-circle text-primary mr-3"></i>
                            <span>Построение оптимальных маршрутов</span>
                        </li>
                        <li class="flex items-center">
                            <i class="fas fa-check-circle text-primary mr-3"></i>
                            <span>Исторические справки и интересные факты</span>
                        </li>
                    </ul>
                    <button id="try-ai-guide" class="bg-primary text-white px-8 py-3 rounded-lg font-semibold hover:bg-secondary transition-colors">
                        Попробовать AI-Гида
                    </button>
                </div>
                <div class="bg-white p-6 rounded-2xl shadow-lg">
                    <div class="bg-gray-100 rounded-lg p-4 h-64 overflow-y-auto" id="chat-container">
                        <div class="flex justify-start mb-4">
                            <div class="bg-primary text-white p-3 rounded-lg max-w-xs">
                                Привет! Я ваш AI-гид. Куда бы вы хотели отправиться в Узбекистане?
                            </div>
                        </div>
                        <div class="flex justify-end mb-4">
                            <div class="bg-gray-200 p-3 rounded-lg max-w-xs">
                                Интересуют исторические места в Самарканде
                            </div>
                        </div>
                        <div class="flex justify-start">
                            <div class="bg-primary text-white p-3 rounded-lg max-w-xs">
                                Отлично! Рекомендую посмотреть Регистан, мавзолей Гур-Эмир и обсерваторию Улугбека. Хотите подробный маршрут?
                            </div>
                        </div>
                    </div>
                    <div class="mt-4 flex">
                        <input type="text" placeholder="Напишите сообщение..." class="flex-1 p-3 border rounded-l-lg" id="chat-input">
                        <button id="send-message" class="bg-primary text-white px-4 rounded-r-lg">
                            <i class="fas fa-paper-plane"></i>
                        </button>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- App Download Section -->
    <section class="py-16 bg-primary text-white">
        <div class="container mx-auto px-4">
            <div class="grid md:grid-cols-2 gap-12 items-center">
                <div>
                    <h2 class="text-3xl font-bold mb-6">Скачайте наше приложение</h2>
                    <p class="text-xl mb-8">Все функции платформы всегда под рукой. Бронируйте отели, планируйте маршруты и получайте рекомендации в любое время.</p>
                    <div class="flex flex-wrap gap-4">
                        <button id="app-store" class="bg-white text-primary px-6 py-3 rounded-lg font-semibold flex items-center">
                            <i class="fab fa-apple text-2xl mr-2"></i>
                            App Store
                        </button>
                        <button id="google-play" class="bg-white text-primary px-6 py-3 rounded-lg font-semibold flex items-center">
                            <i class="fab fa-google-play text-2xl mr-2"></i>
                            Google Play
                        </button>
                    </div>
                </div>
                <div class="flex justify-center">
                    <img src="https://cdn.pixabay.com/photo/2025/08/17/22/55/samarkand-9780493_1280.jpg" alt="Мобильное приложение UberOne" class="w-64 shadow-2xl rounded-3xl" loading="lazy">
                </div>
            </div>
        </div>
    </section>

    <!-- Footer -->
    <footer class="bg-dark text-white py-12 mt-auto">
        <div class="container mx-auto px-4">
            <div class="grid md:grid-cols-4 gap-8">
                <div>
                    <h3 class="text-2xl font-bold mb-4">Uber<span class="text-accent">One</span></h3>
                    <p class="mb-4">Мост между культурой и технологией для вашего идеального путешествия по Узбекистану.</p>
                    <div class="flex space-x-4">
                        <a href="#" class="text-white hover:text-accent transition-colors">
                            <i class="fab fa-instagram text-xl"></i>
                        </a>
                        <a href="#" class="text-white hover:text-accent transition-colors">
                            <i class="fab fa-tiktok text-xl"></i>
                        </a>
                        <a href="#" class="text-white hover:text-accent transition-colors">
                            <i class="fab fa-telegram text-xl"></i>
                        </a>
                        <a href="#" class="text-white hover:text-accent transition-colors">
                            <i class="fab fa-facebook text-xl"></i>
                        </a>
                    </div>
                </div>
                
                <div>
                    <h4 class="font-semibold mb-4">Сервисы</h4>
                    <ul class="space-y-2">
                        <li><a href="#" class="hover:text-accent transition-colors">Бронирование отелей</a></li>
                        <li><a href="#" class="hover:text-accent transition-colors">Экскурсии и туры</a></li>
                        <li><a href="#" class="hover:text-accent transition-colors">Авиабилеты</a></li>
                        <li><a href="#" class="hover:text-accent transition-colors">Трансферы</a></li>
                    </ul>
                </div>
                
                <div>
                    <h4 class="font-semibold mb-4">Поддержка</h4>
                    <ul class="space-y-2">
                        <li><a href="#" class="hover:text-accent transition-colors">Помощь 24/7</a></li>
                        <li><a href="#" class="hover:text-accent transition-colors">Частые вопросы</a></li>
                        <li><a href="#" class="hover:text-accent transition-colors">Отзывы</a></li>
                        <li><a href="#" class="hover:text-accent transition-colors">Контакты</a></li>
                    </ul>
                </div>
                
                <div>
                    <h4 class="font-semibold mb-4">Подписка</h4>
                    <p class="mb-4">Подпишитесь на рассылку для получения лучших предложений</p>
                    <div class="flex">
                        <input type="email" placeholder="Ваш email" class="flex-1 p-2 rounded-l-lg text-dark" id="newsletter-email">
                        <button id="subscribe-btn" class="bg-accent text-dark px-4 rounded-r-lg">
                            <i class="fas fa-paper-plane"></i>
                        </button>
                    </div>
                </div>
            </div>
            
            <div class="border-t border-gray-700 mt-8 pt-8 text-center">
                <p>© 2025 UberOne. Все права защищены.</p>
                <p>by Yusuf Sodikov</p>
            </div>
        </div>
    </footer>

    <!-- Modal for Attraction Details -->
    <div id="attraction-modal" class="fixed inset-0 bg-black bg-opacity-50 flex items-center justify-center z-50 hidden">
        <div class="bg-white rounded-lg p-6 max-w-2xl w-full mx-4 max-h-90vh overflow-y-auto">
            <div class="flex justify-between items-center mb-4">
                <h3 id="modal-title" class="text-2xl font-bold"></h3>
                <button id="close-modal" class="text-gray-500 hover:text-gray-700">
                    <i class="fas fa-times text-xl"></i>
                </button>
            </div>
            <img id="modal-image" src="" alt="" class="w-full h-64 object-cover rounded-lg mb-4">
            <p id="modal-description" class="text-gray-700 mb-4"></p>
            <div class="grid grid-cols-2 gap-4 mb-4">
                <div>
                    <h4 class="font-semibold">Лучшее время для посещения</h4>
                    <p id="modal-best-time" class="text-gray-600"></p>
                </div>
                <div>
                    <h4 class="font-semibold">Входная плата</h4>
                    <p id="modal-price" class="text-gray-600"></p>
                </div>
            </div>
            <button id="book-tour-btn" class="bg-primary text-white px-6 py-2 rounded-lg hover:bg-secondary transition-colors w-full">
                Забронировать экскурсию
            </button>
        </div>
    </div>

    <script>
        // Data for attractions
        const attractions = {
            1: {
                title: "Регистан, Самарканд",
                image: "https://upload.wikimedia.org/wikipedia/commons/thumb/a/a7/Registan_square_Samarkand.jpg/800px-Registan_square_Samarkand.jpg",
                description: "Регистан — сердце древнего Самарканда, одна из самых известных площадей Центральной Азии. Ансамбль из трех медресе: Улугбека (1417-1420), Шер-Дор (1619-1636) и Тилля-Кари (1646-1660) представляет собой великолепный пример исламской архитектуры.",
                bestTime: "Апрель-июнь, сентябрь-октябрь",
                price: "~30,000 UZS"
            },
            2: {
                title: "Мавзолей Гур-Эмир",
                image: "https://upload.wikimedia.org/wikipedia/commons/thumb/5/5c/Gur-e_Amir%2C_Samarkand%2C_Uzbekistan.jpg/800px-Gur-e_Amir%2C_Samarkand%2C_Uzbekistan.jpg",
                description: "Гур-Эмир — мавзолей азиатского conquerorа Тамерлана (также известного как Тимур) и его потомков в Самарканде. Построенный в XV веке, мавзолей знаменит своим бирюзовым куполом и богатым внутренним убранством.",
                bestTime: "Круглый год",
                price: "~25,000 UZS"
            },
            3: {
                title: "Шахи-Зинда",
                image: "https://upload.wikimedia.org/wikipedia/commons/thumb/7/7f/Shah-i-Zinda_%286%29.jpg/800px-Shah-i-Zinda_%286%29.jpg",
                description: "Шахи-Зинда — некрополь на северо-востоке Самарканда, состоящий из мавзолеев знати времен Тамерлана. Название переводится как 'Живой царь' и связано с легендой о двоюродном брате пророка Мухаммеда, который принес ислам в этот регион.",
                bestTime: "Апрель-октябрь",
                price: "~20,000 UZS"
            },
            4: {
                title: "Пои-Калян, Бухара",
                image: "https://upload.wikimedia.org/wikipedia/commons/thumb/0/06/Bukhara_-_Poi_Kalyan_minaret.jpg/800px-Bukhara_-_Poi_Kalyan_minaret.jpg",
                description: "Архитектурный ансамбль Пои-Калян в Бухаре включает минарет Калян (XII век), мечеть Калян (XVI век) и медресе Мири-Араб (XVI век). Минарет Калян высотой 47 метров веками служил главным ориентиром города для караванов Шелкового пути.",
                bestTime: "Март-май, сентябрь-ноябрь",
                price: "Комплексный билет ~40,000 UZS"
            }
        };

        // Language switcher functionality
        document.addEventListener('DOMContentLoaded', function() {
            const languageSelect = document.getElementById('language-select');
            if (languageSelect) {
                languageSelect.addEventListener('change', function() {
                    alert("Язык изменен на: " + this.options[this.selectedIndex].text);
                });
            }
            
            // Navigation click handlers
            document.querySelectorAll('a[href^="#"]').forEach(anchor => {
                anchor.addEventListener('click', function (e) {
                    e.preventDefault();
                    const target = document.querySelector(this.getAttribute('href'));
                    if (target) {
                        target.scrollIntoView({
                            behavior: 'smooth'
                        });
                    }
                });
            });
            
            // Mobile menu toggle
            const mobileMenuButton = document.getElementById('mobile-menu-btn');
            if (mobileMenuButton) {
                mobileMenuButton.addEventListener('click', function() {
                    alert("Мобильное меню открыто");
                });
            }
            
            // Login button
            document.getElementById('login-btn').addEventListener('click', function() {
                alert("Форма входа будет открыта");
            });
            
            // Start planning button
            document.getElementById('start-planning').addEventListener('click', function() {
                document.getElementById('hotels').scrollIntoView({behavior: 'smooth'});
            });
            
            // Download app buttons
            document.getElementById('download-app').addEventListener('click', function() {
                alert("Перенаправление в магазин приложений");
            });
            
            document.getElementById('app-store').addEventListener('click', function() {
                alert("Перенаправление в App Store");
            });
            
            document.getElementById('google-play').addEventListener('click', function() {
                alert("Перенаправление в Google Play");
            });
            
            // Hotel search
            document.getElementById('search-hotels').addEventListener('click', function() {
                const destination = document.getElementById('destination-input').value || "Узбекистан";
                const checkin = document.getElementById('checkin-date').value || "дата заезда";
                const checkout = document.getElementById('checkout-date').value || "дата выезда";
                const guests = document.getElementById('guests-input').value || "2";
                
                alert(`Поиск отелей в ${destination} с ${checkin} по ${checkout} для ${guests} гостей`);
            });
            
            // AI Guide
            document.getElementById('try-ai-guide').addEventListener('click', function() {
                document.getElementById('ai-guide').scrollIntoView({behavior: 'smooth'});
            });
            
            document.getElementById('send-message').addEventListener('click', function() {
                const input = document.getElementById('chat-input');
                if (input.value.trim() !== "") {
                    const chatContainer = document.getElementById('chat-container');
                    
                    // User message
                    const userMsg = document.createElement('div');
                    userMsg.className = 'flex justify-end mb-4';
                    userMsg.innerHTML = `<div class="bg-gray-200 p-3 rounded-lg max-w-xs">${input.value}</div>`;
                    chatContainer.appendChild(userMsg);
                    
                    // AI response (after delay)
                    setTimeout(() => {
                        const aiMsg = document.createElement('div');
                        aiMsg.className = 'flex justify-start mb-4';
                        aiMsg.innerHTML = `<div class="bg-primary text-white p-3 rounded-lg max-w-xs">Спасибо за ваш вопрос! Я помогу вам спланировать ваше путешествие по Узбекистану.</div>`;
                        chatContainer.appendChild(aiMsg);
                        chatContainer.scrollTop = chatContainer.scrollHeight;
                    }, 1000);
                    
                    input.value = "";
                    chatContainer.scrollTop = chatContainer.scrollHeight;
                }
            });
            
            // Attraction buttons
            document.querySelectorAll('.attraction-btn').forEach(btn => {
                btn.addEventListener('click', function() {
                    const attractionId = this.getAttribute('data-id');
                    const attraction = attractions[attractionId];
                    
                    if (attraction) {
                        document.getElementById('modal-title').textContent = attraction.title;
                        document.getElementById('modal-image').src = attraction.image;
                        document.getElementById('modal-image').alt = attraction.title;
                        document.getElementById('modal-description').textContent = attraction.description;
                        document.getElementById('modal-best-time').textContent = attraction.bestTime;
                        document.getElementById('modal-price').textContent = attraction.price;
                        
                        document.getElementById('attraction-modal').classList.remove('hidden');
                    }
                });
            });
            
            // Close modal
            document.getElementById('close-modal').addEventListener('click', function() {
                document.getElementById('attraction-modal').classList.add('hidden');
            });
            
            // Book tour from modal
            document.getElementById('book-tour-btn').addEventListener('click', function() {
                const title = document.getElementById('modal-title').textContent;
                alert(`Бронирование экскурсии: ${title}`);
                document.getElementById('attraction-modal').classList.add('hidden');
            });
            
            // View all attractions
            document.getElementById('view-all-attractions').addEventListener('click', function() {
                alert("Открытие полного каталога достопримечательностей Узбекистана");
            });
            
            // VR Tour
            document.getElementById('start-vr-tour').addEventListener('click', function() {
                alert("Запуск эксклюзивного 3D тура по достопримечательностям Узбекистана!");
            });
            
            // Newsletter subscription
            document.getElementById('subscribe-btn').addEventListener('click', function() {
                const email = document.getElementById('newsletter-email').value;
                if (email && email.includes('@')) {
                    alert(`Спасибо за подписку! На адрес ${email} будут приходить лучшие предложения.`);
                    document.getElementById('newsletter-email').value = "";
                } else {
                    alert("Пожалуйста, введите корректный email адрес");
                }
            });
        });
    </script>
</body>
</html>
