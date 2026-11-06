[Uploading k_explore_events (1).html…]()
<!DOCTYPE html>
<html lang="en" class="light">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>K Explore - Biotech & Life Sciences Events</title>
    <!-- Tailwind CSS -->
    <script src="https://cdn.tailwindcss.com"></script>
    <!-- FontAwesome for Icons -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <!-- Google Fonts -->
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700&display=swap" rel="stylesheet">
    
    <script>
        // Configure Tailwind to support class-based dark mode
        tailwind.config = {
            darkMode: 'class',
            theme: {
                extend: {
                    fontFamily: {
                        sans: ['Inter', 'sans-serif'],
                    },
                    colors: {
                        primary: '#10b981', // Emerald 500
                        primaryDark: '#059669', // Emerald 600
                        darkBg: '#0f172a',  // Slate 900
                        darkCard: '#1e293b' // Slate 800
                    }
                }
            }
        }
    </script>
    <style>
        /* Custom scrollbar and animations */
        body {
            font-family: 'Inter', sans-serif;
            transition: background-color 0.3s, color 0.3s;
        }
        
        ::-webkit-scrollbar {
            width: 8px;
        }
        ::-webkit-scrollbar-track {
            background: transparent; 
        }
        ::-webkit-scrollbar-thumb {
            background: #cbd5e1; 
            border-radius: 4px;
        }
        .dark ::-webkit-scrollbar-thumb {
            background: #475569; 
        }

        .modal-overlay {
            backdrop-filter: blur(5px);
        }

        /* Toast notification slide-in animation */
        @keyframes slideInRight {
            from { transform: translateX(100%); opacity: 0; }
            to { transform: translateX(0); opacity: 1; }
        }
        .toast-enter {
            animation: slideInRight 0.4s ease-out forwards;
        }
    </style>
</head>
<body class="bg-gray-50 text-gray-800 dark:bg-darkBg dark:text-gray-200 antialiased flex flex-col min-h-screen">

    <!-- Sticky Header -->
    <header class="sticky top-0 z-40 w-full bg-white/90 dark:bg-darkCard/90 backdrop-blur-md border-b border-gray-200 dark:border-gray-700 shadow-sm transition-colors duration-300">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 h-16 flex items-center justify-between">
            <div class="flex flex-col justify-center">
                <div class="flex items-center gap-2">
                    <i class="fa-solid fa-dna text-primary text-2xl"></i>
                    <span class="font-bold text-xl tracking-tight text-gray-900 dark:text-white">K Explore</span>
                </div>
                <span class="text-[10px] sm:text-xs text-gray-500 dark:text-gray-400 font-medium tracking-wide uppercase mt-0.5">Himadri Shekhar Paul | Roll No. 2460100</span>
            </div>
            
            <nav class="hidden md:flex gap-6 font-medium text-sm">
                <a href="#" class="hover:text-primary transition-colors text-primary">Events</a>
                <a href="#about" class="hover:text-primary transition-colors">About Us</a>
                <a href="#contact" class="hover:text-primary transition-colors">Contact</a>
            </nav>

            <div class="flex items-center gap-4">
                <button id="theme-toggle" class="p-2 rounded-full hover:bg-gray-200 dark:hover:bg-gray-700 transition-colors focus:outline-none" aria-label="Toggle Dark Mode">
                    <i id="theme-icon" class="fa-solid fa-moon text-gray-600 dark:text-gray-300 text-lg"></i>
                </button>
            </div>
        </div>
    </header>

    <!-- Hero Section -->
    <section class="relative bg-white dark:bg-darkBg pt-16 pb-20 lg:pt-24 lg:pb-28 overflow-hidden transition-colors duration-300">
        <div class="absolute inset-0 z-0">
            <!-- Decorative gradient backgrounds -->
            <div class="absolute top-[-10%] left-[-10%] w-[40%] h-[60%] rounded-full bg-primary/20 blur-3xl"></div>
            <div class="absolute bottom-[-10%] right-[-10%] w-[40%] h-[60%] rounded-full bg-blue-500/10 blur-3xl"></div>
        </div>
        
        <div class="relative z-10 max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 text-center">
            <h1 class="text-4xl md:text-5xl lg:text-6xl font-extrabold text-gray-900 dark:text-white tracking-tight mb-6">
                Discover the Future of <br>
                <span class="text-transparent bg-clip-text bg-gradient-to-r from-primary to-blue-500">Life Sciences & Biotech</span>
            </h1>
            <p class="max-w-2xl mx-auto text-lg md:text-xl text-gray-600 dark:text-gray-400 mb-10">
                Explore upcoming workshops, conferences, and seminars. Connect with industry leaders and accelerate your career in biotechnology.
            </p>
            <a href="#events" class="inline-block bg-primary hover:bg-primaryDark text-white font-medium px-8 py-3 rounded-full shadow-lg hover:shadow-primary/50 transition-all duration-300 transform hover:-translate-y-1">
                Explore Events
            </a>
        </div>
    </section>

    <!-- Main Content: Filters & Events -->
    <main id="events" class="flex-grow max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 py-12 w-full">
        
        <!-- Controls: Search and Filter -->
        <div class="flex flex-col md:flex-row gap-4 justify-between items-center mb-10 bg-white dark:bg-darkCard p-4 rounded-2xl shadow-sm border border-gray-100 dark:border-gray-700 transition-colors duration-300">
            <div class="relative w-full md:w-96">
                <i class="fa-solid fa-search absolute left-4 top-1/2 transform -translate-y-1/2 text-gray-400"></i>
                <input type="text" id="search-input" placeholder="Search events..." class="w-full pl-10 pr-4 py-2.5 rounded-xl border border-gray-300 dark:border-gray-600 bg-gray-50 dark:bg-gray-700 text-gray-900 dark:text-white focus:ring-2 focus:ring-primary focus:border-transparent outline-none transition-all">
            </div>
            
            <div class="relative w-full md:w-64">
                <select id="category-filter" class="w-full pl-4 pr-10 py-2.5 rounded-xl border border-gray-300 dark:border-gray-600 bg-gray-50 dark:bg-gray-700 text-gray-900 dark:text-white focus:ring-2 focus:ring-primary focus:border-transparent outline-none appearance-none transition-all cursor-pointer">
                    <option value="All">All Categories</option>
                    <option value="Workshops">Workshops</option>
                    <option value="Conferences">Conferences</option>
                    <option value="Seminars">Seminars</option>
                </select>
                <i class="fa-solid fa-chevron-down absolute right-4 top-1/2 transform -translate-y-1/2 text-gray-400 pointer-events-none"></i>
            </div>
        </div>

        <!-- Event Grid -->
        <div id="events-grid" class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8">
            <!-- Event Cards injected via JS -->
        </div>

        <!-- Empty State (Hidden by default) -->
        <div id="empty-state" class="hidden text-center py-20">
            <i class="fa-solid fa-box-open text-6xl text-gray-300 dark:text-gray-600 mb-4"></i>
            <h3 class="text-xl font-medium text-gray-900 dark:text-white">No events found</h3>
            <p class="text-gray-500 dark:text-gray-400 mt-2">Try adjusting your search or filter criteria.</p>
        </div>

    </main>

    <!-- Footer -->
    <footer class="bg-white dark:bg-darkCard border-t border-gray-200 dark:border-gray-700 py-8 transition-colors duration-300">
        <div class="max-w-7xl mx-auto px-4 text-center">
            <div class="flex justify-center items-center gap-2 mb-4">
                <i class="fa-solid fa-dna text-primary text-xl"></i>
                <span class="font-bold text-lg text-gray-900 dark:text-white">K Explore</span>
            </div>
            <p class="text-gray-500 dark:text-gray-400 text-sm">
                &copy; 2026 K Explore Event Management. All rights reserved. <br> 
                Assignment submitted by <strong class="text-gray-700 dark:text-gray-300">Himadri Shekhar Paul</strong> (Roll No. 2460100).
            </p>
        </div>
    </footer>

    <!-- Registration Modal -->
    <div id="registration-modal" class="fixed inset-0 z-50 hidden items-center justify-center">
        <!-- Backdrop -->
        <div class="absolute inset-0 bg-black/60 modal-overlay transition-opacity" id="modal-backdrop"></div>
        
        <!-- Modal Content -->
        <div class="relative bg-white dark:bg-darkCard w-11/12 max-w-md rounded-2xl shadow-2xl p-6 md:p-8 transform transition-all scale-95 opacity-0 duration-300" id="modal-content">
            
            <button id="close-modal" class="absolute top-4 right-4 text-gray-400 hover:text-gray-600 dark:hover:text-gray-200 transition-colors focus:outline-none">
                <i class="fa-solid fa-xmark text-xl"></i>
            </button>

            <h2 class="text-2xl font-bold text-gray-900 dark:text-white mb-2">Register for Event</h2>
            <p id="modal-event-title" class="text-primary font-medium mb-6 line-clamp-1"></p>

            <form id="registration-form" class="space-y-4">
                <input type="hidden" id="event-id" value="">
                
                <div>
                    <label for="name" class="block text-sm font-medium text-gray-700 dark:text-gray-300 mb-1">Full Name</label>
                    <input type="text" id="name" required class="w-full px-4 py-2 rounded-lg border border-gray-300 dark:border-gray-600 bg-gray-50 dark:bg-gray-700 text-gray-900 dark:text-white focus:ring-2 focus:ring-primary focus:border-transparent outline-none transition-all">
                </div>
                
                <div>
                    <label for="email" class="block text-sm font-medium text-gray-700 dark:text-gray-300 mb-1">Email Address</label>
                    <input type="email" id="email" required class="w-full px-4 py-2 rounded-lg border border-gray-300 dark:border-gray-600 bg-gray-50 dark:bg-gray-700 text-gray-900 dark:text-white focus:ring-2 focus:ring-primary focus:border-transparent outline-none transition-all">
                    <p id="email-error" class="text-red-500 text-xs mt-1 hidden">Please enter a valid email address.</p>
                </div>
                
                <div>
                    <label for="phone" class="block text-sm font-medium text-gray-700 dark:text-gray-300 mb-1">Phone Number (10 Digits)</label>
                    <input type="tel" id="phone" required class="w-full px-4 py-2 rounded-lg border border-gray-300 dark:border-gray-600 bg-gray-50 dark:bg-gray-700 text-gray-900 dark:text-white focus:ring-2 focus:ring-primary focus:border-transparent outline-none transition-all">
                    <p id="phone-error" class="text-red-500 text-xs mt-1 hidden">Phone number must be exactly 10 digits.</p>
                </div>

                <div class="pt-4">
                    <button type="submit" class="w-full bg-primary hover:bg-primaryDark text-white font-semibold py-2.5 rounded-lg shadow-md transition-colors duration-200">
                        Confirm Registration
                    </button>
                </div>
            </form>
        </div>
    </div>

    <!-- Toast Notification (Replaces alert) -->
    <div id="toast" class="fixed bottom-5 right-5 z-50 hidden bg-white dark:bg-darkCard border-l-4 border-primary shadow-xl rounded-lg p-4 flex items-center gap-3 transition-colors duration-300">
        <div class="bg-primary/20 text-primary rounded-full p-2 h-8 w-8 flex items-center justify-center">
            <i class="fa-solid fa-check"></i>
        </div>
        <div>
            <h4 class="text-gray-900 dark:text-white font-semibold text-sm">Success!</h4>
            <p class="text-gray-500 dark:text-gray-400 text-xs" id="toast-message">Registration completed successfully.</p>
        </div>
    </div>

    <!-- JavaScript Logic -->
    <script>
        // --- Data: Biotech & Life Sciences Events ---
        const eventsData = [
            {
                id: 1,
                title: "Bhubaneswar Biotech Summit",
                category: "Conferences",
                date: "Nov 15, 2026",
                venue: "Kalinga Convention Center",
                desc: "Join leading experts for a 3-day summit on advancing biotechnology in India. Networking, keynote speeches, and more.",
                img: "https://placehold.co/600x400/0f172a/10b981?text=Biotech+Summit"
            },
            {
                id: 2,
                title: "CRISPR & Genetics Workshop",
                category: "Workshops",
                date: "Dec 05, 2026",
                venue: "Life Sciences Institute",
                desc: "Hands-on workshop detailing the latest CRISPR-Cas9 techniques. Ideal for researchers and grad students.",
                img: "https://placehold.co/600x400/1e293b/3b82f6?text=CRISPR+Workshop"
            },
            {
                id: 3,
                title: "Future of Synthetic Biology",
                category: "Seminars",
                date: "Dec 20, 2026",
                venue: "Tech Park Auditorium",
                desc: "A focused seminar on the ethical and technological future of synthetic biology and lab-grown organs.",
                img: "https://placehold.co/600x400/0f172a/8b5cf6?text=Synthetic+Bio"
            },
            {
                id: 4,
                title: "Bioinformatics Bootcamp",
                category: "Workshops",
                date: "Jan 10, 2027",
                venue: "Digital Campus, Block B",
                desc: "Learn computational biology tools, genomic data analysis, and Python for bioinformatics in this intensive bootcamp.",
                img: "https://placehold.co/600x400/1e293b/ec4899?text=Bioinformatics"
            },
            {
                id: 5,
                title: "Global Pharma Tech",
                category: "Conferences",
                date: "Feb 22, 2027",
                venue: "Grand Royal Hotel",
                desc: "Annual conference gathering pharmaceutical giants to discuss AI in drug discovery and manufacturing.",
                img: "https://placehold.co/600x400/0f172a/f59e0b?text=Pharma+Tech"
            },
            {
                id: 6,
                title: "Nanomedicine Innovations",
                category: "Seminars",
                date: "Mar 18, 2027",
                venue: "Science Museum Hall",
                desc: "Discover how nanotechnology is revolutionizing targeted drug delivery and advanced diagnostics.",
                img: "https://placehold.co/600x400/1e293b/14b8a6?text=Nanomedicine"
            }
        ];

        // --- DOM Elements ---
        const themeToggleBtn = document.getElementById('theme-toggle');
        const themeIcon = document.getElementById('theme-icon');
        const eventsGrid = document.getElementById('events-grid');
        const searchInput = document.getElementById('search-input');
        const categoryFilter = document.getElementById('category-filter');
        const emptyState = document.getElementById('empty-state');
        
        // Modal Elements
        const modal = document.getElementById('registration-modal');
        const modalBackdrop = document.getElementById('modal-backdrop');
        const modalContent = document.getElementById('modal-content');
        const closeModalBtn = document.getElementById('close-modal');
        const regForm = document.getElementById('registration-form');
        const modalEventTitle = document.getElementById('modal-event-title');
        const eventIdInput = document.getElementById('event-id');
        
        // Form Validation Elements
        const emailInput = document.getElementById('email');
        const phoneInput = document.getElementById('phone');
        const emailError = document.getElementById('email-error');
        const phoneError = document.getElementById('phone-error');
        
        // Toast
        const toast = document.getElementById('toast');
        const toastMessage = document.getElementById('toast-message');

        // --- Theme Toggle Logic ---
        function initializeTheme() {
            // Check LocalStorage or system preference
            if (localStorage.getItem('theme') === 'dark' || (!('theme' in localStorage) && window.matchMedia('(prefers-color-scheme: dark)').matches)) {
                document.documentElement.classList.add('dark');
                themeIcon.classList.replace('fa-moon', 'fa-sun');
            } else {
                document.documentElement.classList.remove('dark');
                themeIcon.classList.replace('fa-sun', 'fa-moon');
            }
        }

        themeToggleBtn.addEventListener('click', () => {
            document.documentElement.classList.toggle('dark');
            if (document.documentElement.classList.contains('dark')) {
                localStorage.setItem('theme', 'dark');
                themeIcon.classList.replace('fa-moon', 'fa-sun');
            } else {
                localStorage.setItem('theme', 'light');
                themeIcon.classList.replace('fa-sun', 'fa-moon');
            }
        });

        // Initialize on load
        initializeTheme();

        // --- Event Rendering & Filtering ---
        function createEventCard(event) {
            // Category color coding
            let badgeColor = "bg-primary text-white";
            if(event.category === "Workshops") badgeColor = "bg-blue-500 text-white";
            if(event.category === "Seminars") badgeColor = "bg-purple-500 text-white";

            return `
                <div class="bg-white dark:bg-darkCard rounded-2xl overflow-hidden shadow-md hover:shadow-xl transition-all duration-300 border border-gray-100 dark:border-gray-700 flex flex-col h-full transform hover:-translate-y-1">
                    <div class="relative h-48 overflow-hidden">
                        <img src="${event.img}" alt="${event.title}" class="w-full h-full object-cover transition-transform duration-500 hover:scale-110">
                        <div class="absolute top-4 right-4 ${badgeColor} text-xs font-bold px-3 py-1 rounded-full shadow-sm">
                            ${event.category}
                        </div>
                    </div>
                    <div class="p-6 flex flex-col flex-grow">
                        <h3 class="text-xl font-bold text-gray-900 dark:text-white mb-2 line-clamp-1">${event.title}</h3>
                        
                        <div class="flex items-center text-sm text-gray-500 dark:text-gray-400 mb-1">
                            <i class="fa-regular fa-calendar w-5 text-primary"></i>
                            <span>${event.date}</span>
                        </div>
                        <div class="flex items-center text-sm text-gray-500 dark:text-gray-400 mb-4">
                            <i class="fa-solid fa-location-dot w-5 text-primary"></i>
                            <span class="line-clamp-1">${event.venue}</span>
                        </div>
                        
                        <p class="text-gray-600 dark:text-gray-300 text-sm mb-6 flex-grow line-clamp-3">
                            ${event.desc}
                        </p>
                        
                        <button onclick="openModal(${event.id}, '${event.title.replace(/'/g, "\\'")}')" class="mt-auto w-full bg-gray-50 hover:bg-primary dark:bg-gray-700 dark:hover:bg-primary text-gray-800 dark:text-white hover:text-white font-medium py-2.5 rounded-lg border border-gray-200 dark:border-gray-600 hover:border-transparent transition-colors duration-300">
                            Register Now
                        </button>
                    </div>
                </div>
            `;
        }

        function renderEvents() {
            const searchText = searchInput.value.toLowerCase();
            const selectedCategory = categoryFilter.value;

            const filteredEvents = eventsData.filter(event => {
                const matchesSearch = event.title.toLowerCase().includes(searchText) || event.desc.toLowerCase().includes(searchText) || event.venue.toLowerCase().includes(searchText);
                const matchesCategory = selectedCategory === "All" || event.category === selectedCategory;
                return matchesSearch && matchesCategory;
            });

            eventsGrid.innerHTML = '';
            
            if (filteredEvents.length === 0) {
                eventsGrid.classList.add('hidden');
                emptyState.classList.remove('hidden');
            } else {
                eventsGrid.classList.remove('hidden');
                emptyState.classList.add('hidden');
                filteredEvents.forEach(event => {
                    eventsGrid.innerHTML += createEventCard(event);
                });
            }
        }

        // Event Listeners for search and filter
        searchInput.addEventListener('input', renderEvents);
        categoryFilter.addEventListener('change', renderEvents);

        // Initial render
        renderEvents();

        // --- Modal & Registration Logic ---
        window.openModal = function(id, title) {
            modalEventTitle.textContent = title;
            eventIdInput.value = id;
            
            // Reset form and errors
            regForm.reset();
            emailError.classList.add('hidden');
            phoneError.classList.add('hidden');
            emailInput.classList.remove('border-red-500');
            phoneInput.classList.remove('border-red-500');

            // Show modal with animation
            modal.classList.remove('hidden');
            modal.classList.add('flex');
            // Trigger reflow for animation
            void modal.offsetWidth;
            modalContent.classList.remove('scale-95', 'opacity-0');
            modalContent.classList.add('scale-100', 'opacity-100');
        }

        function closeModal() {
            modalContent.classList.remove('scale-100', 'opacity-100');
            modalContent.classList.add('scale-95', 'opacity-0');
            
            setTimeout(() => {
                modal.classList.add('hidden');
                modal.classList.remove('flex');
            }, 300); // match duration-300
        }

        closeModalBtn.addEventListener('click', closeModal);
        modalBackdrop.addEventListener('click', closeModal);

        // Custom Validation Regex
        const emailRegex = /^[^\s@]+@[^\s@]+\.[^\s@]+$/;
        const phoneRegex = /^\d{10}$/;

        function showToast(message) {
            toastMessage.textContent = message;
            toast.classList.remove('hidden');
            toast.classList.add('toast-enter');
            
            setTimeout(() => {
                toast.classList.add('hidden');
                toast.classList.remove('toast-enter');
            }, 4000);
        }

        regForm.addEventListener('submit', (e) => {
            e.preventDefault();
            
            let isValid = true;
            const emailVal = emailInput.value.trim();
            const phoneVal = phoneInput.value.trim();
            const nameVal = document.getElementById('name').value.trim();
            const eventTitle = modalEventTitle.textContent;

            // Validate Email
            if (!emailRegex.test(emailVal)) {
                emailError.classList.remove('hidden');
                emailInput.classList.add('border-red-500', 'dark:border-red-500');
                isValid = false;
            } else {
                emailError.classList.add('hidden');
                emailInput.classList.remove('border-red-500', 'dark:border-red-500');
            }

            // Validate Phone (Exactly 10 digits)
            if (!phoneRegex.test(phoneVal)) {
                phoneError.classList.remove('hidden');
                phoneInput.classList.add('border-red-500', 'dark:border-red-500');
                isValid = false;
            } else {
                phoneError.classList.add('hidden');
                phoneInput.classList.remove('border-red-500', 'dark:border-red-500');
            }

            if (isValid) {
                // Save to LocalStorage
                const registrationData = {
                    id: Date.now(),
                    name: nameVal,
                    email: emailVal,
                    phone: phoneVal,
                    eventTitle: eventTitle,
                    registeredAt: new Date().toISOString()
                };

                let registrations = JSON.parse(localStorage.getItem('kexplore_registrations')) || [];
                registrations.push(registrationData);
                localStorage.setItem('kexplore_registrations', JSON.stringify(registrations));

                closeModal();
                showToast(`Successfully registered for ${eventTitle}`);
            }
        });

    </script>
</body>
</html>
