<template>
  <div class="min-h-screen bg-slate-950 text-white font-['Inter',system-ui,sans-serif] overflow-x-hidden">

    <!-- Navigation -->
    <nav class="fixed top-0 w-full z-50 bg-slate-950/80 backdrop-blur-md border-b border-white/5">
      <div class="max-w-6xl mx-auto px-6 py-4 flex items-center justify-between">
        <a href="#" class="text-xl font-bold tracking-tight">JB<span class="text-purple-400">.</span></a>
        <div class="hidden md:flex items-center gap-8">
          <a href="#projects" class="text-sm text-gray-400 hover:text-white transition-colors">Projects</a>
          <a href="#about" class="text-sm text-gray-400 hover:text-white transition-colors">About</a>
          <a href="#contact" class="px-5 py-2 text-sm bg-purple-600 hover:bg-purple-700 rounded-lg transition-colors">Contact</a>
        </div>
        <button @click="mobileOpen = !mobileOpen" class="md:hidden text-gray-400 hover:text-white">
          <svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24">
            <path v-if="!mobileOpen" stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 6h16M4 12h16M4 18h16"/>
            <path v-else stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M6 18L18 6M6 6l12 12"/>
          </svg>
        </button>
      </div>
      <div v-if="mobileOpen" class="md:hidden border-t border-white/5 bg-slate-950/95 backdrop-blur-md">
        <div class="px-6 py-4 flex flex-col gap-4">
          <a href="#projects" @click="mobileOpen = false" class="text-gray-400 hover:text-white transition-colors">Projects</a>
          <a href="#about" @click="mobileOpen = false" class="text-gray-400 hover:text-white transition-colors">About</a>
          <a href="#contact" @click="mobileOpen = false" class="text-gray-400 hover:text-white transition-colors">Contact</a>
        </div>
      </div>
    </nav>

    <!-- Hero Section -->
    <section class="pt-28 pb-16 md:pt-36 md:pb-24 px-6">
      <div class="max-w-4xl mx-auto">
        <div class="inline-flex items-center gap-2 px-4 py-2 bg-purple-500/10 border border-purple-500/20 rounded-full mb-8">
          <div class="w-2 h-2 bg-green-400 rounded-full animate-pulse"></div>
          <span class="text-purple-300 text-sm font-medium">Eskwelabs Innovation Fellow</span>
        </div>
        <h1 class="text-5xl md:text-7xl font-extrabold tracking-tight mb-6 leading-[1.1]">
          Justin Bon<br class="hidden md:block" />
          <span class="text-purple-400">Dela Cruz</span>
        </h1>
        <p class="text-lg md:text-2xl text-gray-400 font-light max-w-2xl mb-10 leading-relaxed">
          Full-stack developer and AI engineer building intelligent web applications.
          I turn ideas into shipped products.
        </p>
        <div class="flex flex-col sm:flex-row gap-3">
          <a href="#projects" class="px-8 py-3.5 bg-purple-600 hover:bg-purple-700 rounded-lg font-medium transition-all hover:shadow-lg hover:shadow-purple-600/25 text-center">
            View My Work
          </a>
          <a href="#contact" class="px-8 py-3.5 border border-white/15 hover:border-white/30 rounded-lg font-medium transition-all text-center">
            Get In Touch
          </a>
        </div>
      </div>
    </section>

    <!-- Projects Section -->
    <section id="projects" class="py-16 md:py-24 px-6">
      <div class="max-w-6xl mx-auto">
        <p class="text-purple-400 font-medium text-sm tracking-wide uppercase mb-3">Portfolio</p>
        <h2 class="text-3xl md:text-4xl font-bold mb-4">Featured Projects</h2>
        <p class="text-gray-400 mb-10 md:mb-14 max-w-xl">Products I've built from the ground up — from AI-powered platforms to full-stack web applications.</p>

        <!-- Talux Notes -->
        <div class="mb-6">
          <a href="https://talux.app" target="_blank" rel="noopener noreferrer"
             class="group block p-6 md:p-10 bg-gradient-to-br from-purple-900/30 via-slate-800/40 to-slate-900/40 border border-white/10 rounded-2xl hover:border-purple-500/40 transition-all duration-300">
            <div class="flex items-center gap-3 mb-2">
              <div class="w-12 h-12 flex-shrink-0 bg-purple-600 rounded-xl flex items-center justify-center font-bold text-xl">T</div>
              <div class="flex-1 min-w-0">
                <h3 class="text-xl md:text-2xl font-bold">Talux Notes</h3>
                <p class="text-sm text-gray-500">AI-Powered Knowledge Platform</p>
              </div>
            </div>
            <div class="flex items-center gap-2 text-sm text-purple-400 mb-5 pl-1">
              <span class="w-2 h-2 bg-green-400 rounded-full flex-shrink-0"></span>
              Live at talux.app
              <svg class="w-4 h-4 group-hover:translate-x-1 transition-transform" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M17 8l4 4m0 0l-4 4m4-4H3"/></svg>
            </div>
            <p class="text-gray-400 leading-relaxed mb-6 max-w-3xl text-sm md:text-base">
              An AI-powered knowledge management platform with smart document import (PDF/DOCX), semantic search, and automated entry connection discovery. Features RAG-based conversational AI using Gemini 2.5 Flash, vector similarity pipelines with ChromaDB, multi-tenant auth with JWT, and voice recognition navigation.
            </p>
            <ScreenshotGallery v-if="screenshots.talux.length" :media="screenshots.talux" class="mb-6" />
            <div class="flex flex-wrap gap-2">
              <span class="px-3 py-1 text-xs bg-white/5 border border-white/10 rounded-full text-gray-300">Python</span>
              <span class="px-3 py-1 text-xs bg-white/5 border border-white/10 rounded-full text-gray-300">React</span>
              <span class="px-3 py-1 text-xs bg-white/5 border border-white/10 rounded-full text-gray-300">SQLite</span>
              <span class="px-3 py-1 text-xs bg-white/5 border border-white/10 rounded-full text-gray-300">Tailwind CSS</span>
              <span class="px-3 py-1 text-xs bg-white/5 border border-white/10 rounded-full text-gray-300">Gemini API</span>
              <span class="px-3 py-1 text-xs bg-white/5 border border-white/10 rounded-full text-gray-300">ChromaDB</span>
              <span class="px-3 py-1 text-xs bg-white/5 border border-white/10 rounded-full text-gray-300">Sentence-Transformers</span>
            </div>
          </a>
        </div>

        <!-- FeedMe -->
        <div class="mb-6">
          <div class="p-6 md:p-10 bg-gradient-to-br from-amber-900/20 via-slate-800/40 to-slate-900/40 border border-white/10 rounded-2xl">
            <div class="flex items-center gap-3 mb-2">
              <div class="w-12 h-12 flex-shrink-0 bg-amber-600 rounded-xl flex items-center justify-center font-bold text-xl">F</div>
              <div class="flex-1 min-w-0">
                <h3 class="text-xl md:text-2xl font-bold">FeedMe</h3>
                <p class="text-sm text-gray-500">Credit Card Food Promo Aggregator</p>
              </div>
            </div>
            <p class="text-sm text-gray-500 mb-5 pl-1">Currently offline</p>
            <p class="text-gray-400 leading-relaxed mb-6 max-w-3xl text-sm md:text-base">
              A full-stack web application that filters dining promos by credit card, enhancing user convenience. Achieved 85% data extraction coverage despite inconsistent website structures via adaptive Puppeteer scraping algorithms.
            </p>
            <ScreenshotGallery v-if="screenshots.feedme.length" :media="screenshots.feedme" class="mb-6" />
            <div class="flex flex-wrap gap-2">
              <span class="px-3 py-1 text-xs bg-white/5 border border-white/10 rounded-full text-gray-300">MongoDB</span>
              <span class="px-3 py-1 text-xs bg-white/5 border border-white/10 rounded-full text-gray-300">Express</span>
              <span class="px-3 py-1 text-xs bg-white/5 border border-white/10 rounded-full text-gray-300">Vue.js</span>
              <span class="px-3 py-1 text-xs bg-white/5 border border-white/10 rounded-full text-gray-300">Node.js</span>
              <span class="px-3 py-1 text-xs bg-white/5 border border-white/10 rounded-full text-gray-300">AWS</span>
              <span class="px-3 py-1 text-xs bg-white/5 border border-white/10 rounded-full text-gray-300">Puppeteer</span>
              <span class="px-3 py-1 text-xs bg-white/5 border border-white/10 rounded-full text-gray-300">Tailwind</span>
            </div>
          </div>
        </div>

        <!-- Secondary Projects -->
        <div class="grid md:grid-cols-2 gap-6">
          <!-- Syllabuddy -->
          <div class="p-6 md:p-8 bg-slate-800/30 border border-white/10 rounded-2xl flex flex-col overflow-hidden">
            <div class="flex items-center gap-3 mb-4">
              <div class="w-10 h-10 flex-shrink-0 bg-blue-600 rounded-xl flex items-center justify-center font-bold">S</div>
              <h3 class="text-xl font-bold">Syllabuddy</h3>
            </div>
            <p class="text-gray-400 leading-relaxed mb-5 text-sm md:text-base">
              An AI-powered tool that parses course syllabi and automatically extracts important dates and deadlines — uploading them directly to Google Calendar. Designed for the less technical user: just upload a PDF.
            </p>
            <ScreenshotGallery v-if="screenshots.syllabuddy.length" :media="screenshots.syllabuddy" class="mb-5" />
            <div class="flex flex-wrap gap-2 mt-auto">
              <span class="px-3 py-1 text-xs bg-white/5 border border-white/10 rounded-full text-gray-300">Svelte</span>
              <span class="px-3 py-1 text-xs bg-white/5 border border-white/10 rounded-full text-gray-300">Node.js</span>
              <span class="px-3 py-1 text-xs bg-white/5 border border-white/10 rounded-full text-gray-300">Express</span>
              <span class="px-3 py-1 text-xs bg-white/5 border border-white/10 rounded-full text-gray-300">MongoDB</span>
              <span class="px-3 py-1 text-xs bg-white/5 border border-white/10 rounded-full text-gray-300">Gemini API</span>
              <span class="px-3 py-1 text-xs bg-white/5 border border-white/10 rounded-full text-gray-300">Google OAuth</span>
              <span class="px-3 py-1 text-xs bg-white/5 border border-white/10 rounded-full text-gray-300">Tailwind</span>
            </div>
          </div>

          <!-- DBSolutions -->
          <div class="p-6 md:p-8 bg-slate-800/30 border border-white/10 rounded-2xl flex flex-col overflow-hidden">
            <div class="flex items-center gap-3 mb-4">
              <div class="w-10 h-10 flex-shrink-0 bg-emerald-600 rounded-xl flex items-center justify-center font-bold">D</div>
              <h3 class="text-xl font-bold">DBSolutions</h3>
            </div>
            <p class="text-gray-400 leading-relaxed mb-5 text-sm md:text-base">
              A clean, functional database management system built and shipped in under a month. Features robust model logic with zero-error data handling and a polished, user-friendly frontend designed entirely from scratch.
            </p>
            <ScreenshotGallery v-if="screenshots.dbsolutions.length" :media="screenshots.dbsolutions" class="mb-5" />
            <div class="flex flex-wrap gap-2 mt-auto">
              <span class="px-3 py-1 text-xs bg-white/5 border border-white/10 rounded-full text-gray-300">Python</span>
              <span class="px-3 py-1 text-xs bg-white/5 border border-white/10 rounded-full text-gray-300">Django</span>
              <span class="px-3 py-1 text-xs bg-white/5 border border-white/10 rounded-full text-gray-300">MySQL</span>
              <span class="px-3 py-1 text-xs bg-white/5 border border-white/10 rounded-full text-gray-300">Bootstrap</span>
              <span class="px-3 py-1 text-xs bg-white/5 border border-white/10 rounded-full text-gray-300">JavaScript</span>
            </div>
          </div>
        </div>

        <div class="mt-10 text-center">
          <a href="https://github.com/TwilightDC02" target="_blank" rel="noopener noreferrer"
             class="inline-flex items-center gap-2 text-gray-400 hover:text-white transition-colors text-sm">
            <svg class="w-5 h-5" fill="currentColor" viewBox="0 0 24 24"><path d="M12 0c-6.626 0-12 5.373-12 12 0 5.302 3.438 9.8 8.207 11.387.599.111.793-.261.793-.577v-2.234c-3.338.726-4.033-1.416-4.033-1.416-.546-1.387-1.333-1.756-1.333-1.756-1.089-.745.083-.729.083-.729 1.205.084 1.839 1.237 1.839 1.237 1.07 1.834 2.807 1.304 3.492.997.107-.775.418-1.305.762-1.604-2.665-.305-5.467-1.334-5.467-5.931 0-1.311.469-2.381 1.236-3.221-.124-.303-.535-1.524.117-3.176 0 0 1.008-.322 3.301 1.23.957-.266 1.983-.399 3.003-.404 1.02.005 2.047.138 3.006.404 2.291-1.552 3.297-1.23 3.297-1.23.653 1.653.242 2.874.118 3.176.77.84 1.235 1.911 1.235 3.221 0 4.609-2.807 5.624-5.479 5.921.43.372.823 1.102.823 2.222v3.293c0 .319.192.694.801.576 4.765-1.589 8.199-6.086 8.199-11.386 0-6.627-5.373-12-12-12z"/></svg>
            View more on GitHub
            <svg class="w-4 h-4" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M17 8l4 4m0 0l-4 4m4-4H3"/></svg>
          </a>
        </div>
      </div>
    </section>

    <!-- About Section -->
    <section id="about" class="py-16 md:py-24 px-6 border-t border-white/5">
      <div class="max-w-6xl mx-auto">
        <p class="text-purple-400 font-medium text-sm tracking-wide uppercase mb-3">About</p>
        <h2 class="text-3xl md:text-4xl font-bold mb-10 md:mb-14">Background & Skills</h2>
        <div class="grid md:grid-cols-2 gap-10 md:gap-16">
          <div>
            <p class="text-gray-300 leading-relaxed mb-6 text-sm md:text-base">
              I'm a Computer Science (Honors) student at <span class="text-white font-medium">Ateneo de Manila University</span>, specializing in Data Science and Analytics (Cum Laude, 3.62 GPA). Currently serving as an <span class="text-white font-medium">Eskwelabs Innovation Fellow</span>, developing prompts and playbooks to make AI systems reliable and useful.
            </p>
            <p class="text-gray-300 leading-relaxed mb-6 text-sm md:text-base">
              I've co-founded a sports apparel startup that achieved a 347% ROI, led fundraising teams, and shipped AI-powered applications to production.
            </p>
            <p class="text-gray-400 leading-relaxed text-sm md:text-base">
              Whether you need a full-stack web application, an AI integration, a data pipeline, or a complete digital product — I deliver clean, scalable solutions from concept to deployment.
            </p>
          </div>
          <div class="space-y-8">
            <div>
              <h3 class="text-sm font-semibold text-gray-500 uppercase tracking-wide mb-4">Languages & Frameworks</h3>
              <div class="flex flex-wrap gap-2">
                <span class="px-3 py-1.5 bg-white/5 border border-white/10 rounded-lg text-sm text-gray-300">Python</span>
                <span class="px-3 py-1.5 bg-white/5 border border-white/10 rounded-lg text-sm text-gray-300">JavaScript</span>
                <span class="px-3 py-1.5 bg-white/5 border border-white/10 rounded-lg text-sm text-gray-300">SQL</span>
                <span class="px-3 py-1.5 bg-white/5 border border-white/10 rounded-lg text-sm text-gray-300">Vue.js</span>
                <span class="px-3 py-1.5 bg-white/5 border border-white/10 rounded-lg text-sm text-gray-300">React</span>
                <span class="px-3 py-1.5 bg-white/5 border border-white/10 rounded-lg text-sm text-gray-300">Svelte</span>
                <span class="px-3 py-1.5 bg-white/5 border border-white/10 rounded-lg text-sm text-gray-300">Node.js</span>
                <span class="px-3 py-1.5 bg-white/5 border border-white/10 rounded-lg text-sm text-gray-300">Django</span>
                <span class="px-3 py-1.5 bg-white/5 border border-white/10 rounded-lg text-sm text-gray-300">Express</span>
              </div>
            </div>
            <div>
              <h3 class="text-sm font-semibold text-gray-500 uppercase tracking-wide mb-4">AI & Data</h3>
              <div class="flex flex-wrap gap-2">
                <span class="px-3 py-1.5 bg-white/5 border border-white/10 rounded-lg text-sm text-gray-300">Machine Learning</span>
                <span class="px-3 py-1.5 bg-white/5 border border-white/10 rounded-lg text-sm text-gray-300">LLM Prompting</span>
                <span class="px-3 py-1.5 bg-white/5 border border-white/10 rounded-lg text-sm text-gray-300">RAG Systems</span>
                <span class="px-3 py-1.5 bg-white/5 border border-white/10 rounded-lg text-sm text-gray-300">PyTorch</span>
                <span class="px-3 py-1.5 bg-white/5 border border-white/10 rounded-lg text-sm text-gray-300">Data Visualization</span>
                <span class="px-3 py-1.5 bg-white/5 border border-white/10 rounded-lg text-sm text-gray-300">Tableau</span>
              </div>
            </div>
            <div>
              <h3 class="text-sm font-semibold text-gray-500 uppercase tracking-wide mb-4">Tools & Infrastructure</h3>
              <div class="flex flex-wrap gap-2">
                <span class="px-3 py-1.5 bg-white/5 border border-white/10 rounded-lg text-sm text-gray-300">AWS</span>
                <span class="px-3 py-1.5 bg-white/5 border border-white/10 rounded-lg text-sm text-gray-300">MongoDB</span>
                <span class="px-3 py-1.5 bg-white/5 border border-white/10 rounded-lg text-sm text-gray-300">MySQL</span>
                <span class="px-3 py-1.5 bg-white/5 border border-white/10 rounded-lg text-sm text-gray-300">ChromaDB</span>
                <span class="px-3 py-1.5 bg-white/5 border border-white/10 rounded-lg text-sm text-gray-300">Git</span>
                <span class="px-3 py-1.5 bg-white/5 border border-white/10 rounded-lg text-sm text-gray-300">REST APIs</span>
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- Contact Section -->
    <section id="contact" class="py-16 md:py-24 px-6 border-t border-white/5">
      <div class="max-w-3xl mx-auto text-center">
        <p class="text-purple-400 font-medium text-sm tracking-wide uppercase mb-3">Contact</p>
        <h2 class="text-3xl md:text-4xl font-bold mb-5">Let's Work Together</h2>
        <p class="text-gray-400 mb-10 md:mb-12 text-base md:text-lg leading-relaxed">
          Have a project in mind or looking for a developer? I'm currently available for freelance work, collaborations, and new opportunities.
        </p>
        <a href="mailto:justinbondc322@gmail.com"
           class="inline-flex items-center justify-center gap-3 px-6 md:px-10 py-4 bg-purple-600 hover:bg-purple-700 rounded-xl font-medium text-base md:text-lg transition-all hover:shadow-lg hover:shadow-purple-600/25 w-full sm:w-auto break-all sm:break-normal">
          <svg class="w-5 h-5 flex-shrink-0" fill="none" stroke="currentColor" viewBox="0 0 24 24">
            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M3 8l7.89 5.26a2 2 0 002.22 0L21 8M5 19h14a2 2 0 002-2V7a2 2 0 00-2-2H5a2 2 0 00-2 2v10a2 2 0 002 2z"/>
          </svg>
          justinbondc322@gmail.com
        </a>
        <div class="flex items-center justify-center gap-6 mt-10">
          <a href="https://github.com/TwilightDC02" target="_blank" rel="noopener noreferrer"
             class="p-3 text-gray-500 hover:text-white bg-white/5 hover:bg-white/10 rounded-xl transition-all" aria-label="GitHub">
            <svg class="w-6 h-6" fill="currentColor" viewBox="0 0 24 24"><path d="M12 0c-6.626 0-12 5.373-12 12 0 5.302 3.438 9.8 8.207 11.387.599.111.793-.261.793-.577v-2.234c-3.338.726-4.033-1.416-4.033-1.416-.546-1.387-1.333-1.756-1.333-1.756-1.089-.745.083-.729.083-.729 1.205.084 1.839 1.237 1.839 1.237 1.07 1.834 2.807 1.304 3.492.997.107-.775.418-1.305.762-1.604-2.665-.305-5.467-1.334-5.467-5.931 0-1.311.469-2.381 1.236-3.221-.124-.303-.535-1.524.117-3.176 0 0 1.008-.322 3.301 1.23.957-.266 1.983-.399 3.003-.404 1.02.005 2.047.138 3.006.404 2.291-1.552 3.297-1.23 3.297-1.23.653 1.653.242 2.874.118 3.176.77.84 1.235 1.911 1.235 3.221 0 4.609-2.807 5.624-5.479 5.921.43.372.823 1.102.823 2.222v3.293c0 .319.192.694.801.576 4.765-1.589 8.199-6.086 8.199-11.386 0-6.627-5.373-12-12-12z"/></svg>
          </a>
          <a href="https://linkedin.com/in/justinbondelacruz" target="_blank" rel="noopener noreferrer"
             class="p-3 text-gray-500 hover:text-white bg-white/5 hover:bg-white/10 rounded-xl transition-all" aria-label="LinkedIn">
            <svg class="w-6 h-6" fill="currentColor" viewBox="0 0 24 24"><path d="M20.447 20.452h-3.554v-5.569c0-1.328-.027-3.037-1.852-3.037-1.853 0-2.136 1.445-2.136 2.939v5.667H9.351V9h3.414v1.561h.046c.477-.9 1.637-1.85 3.37-1.85 3.601 0 4.267 2.37 4.267 5.455v6.286zM5.337 7.433c-1.144 0-2.063-.926-2.063-2.065 0-1.138.92-2.063 2.063-2.063 1.14 0 2.064.925 2.064 2.063 0 1.139-.925 2.065-2.064 2.065zm1.782 13.019H3.555V9h3.564v11.452zM22.225 0H1.771C.792 0 0 .774 0 1.729v20.542C0 23.227.792 24 1.771 24h20.451C23.2 24 24 23.227 24 22.271V1.729C24 .774 23.2 0 22.222 0h.003z"/></svg>
          </a>
        </div>
      </div>
    </section>

    <!-- Lightbox -->
    <div v-if="lightbox" @click="lightbox = null"
         class="fixed inset-0 z-50 bg-black/90 flex items-center justify-center p-4 cursor-zoom-out">
      <video
        v-if="isVideo(lightbox)"
        :src="lightbox"
        controls
        autoplay
        class="max-w-full max-h-full rounded-xl shadow-2xl"
        @click.stop
      />
      <img
        v-else
        :src="lightbox"
        class="max-w-full max-h-full rounded-xl shadow-2xl object-contain"
      />
      <button @click.stop="lightbox = null" class="absolute top-4 right-4 text-white/60 hover:text-white">
        <svg class="w-8 h-8" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M6 18L18 6M6 6l12 12"/></svg>
      </button>
    </div>
  </div>
</template>

<script setup>
import { ref, provide } from 'vue'
import ScreenshotGallery from './ScreenshotGallery.vue'

const mobileOpen = ref(false)
const lightbox = ref(null)

const screenshots = ref({
  talux: [
    '/screenshots/talux/demo.mov',
    '/screenshots/talux/1.png',
    '/screenshots/talux/2.png',
    '/screenshots/talux/3.png',
    '/screenshots/talux/4.png',
    '/screenshots/talux/5.png',
  ],
  feedme: [
    '/screenshots/feedme/demo.mov',
    '/screenshots/feedme/1.png',
    '/screenshots/feedme/2.png',
  ],
  syllabuddy: [
    '/screenshots/syllabuddy/demo.mov',
  ],
  dbsolutions: [
    '/screenshots/dbsolutions/1.png',
    '/screenshots/dbsolutions/2.png',
    '/screenshots/dbsolutions/3.png',
  ],
})

provide('openLightbox', (src) => { lightbox.value = src })

function isVideo(src) {
  return /\.(mp4|webm|mov|ogg)$/i.test(src)
}
</script>
