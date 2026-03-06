# 3d-real-state
A high-performance, responsive landing page template designed for modern real estate marketing. This project integrates interactive 3D architectural visualization directly into the browser to enhance property showcases.
<body class="bg-gray-50 text-gray-900 font-sans">

    <nav class="p-6 bg-white shadow-sm flex justify-between items-center sticky top-0 z-50">
        <h1 class="text-2xl font-bold text-blue-600 flex items-center gap-2">
            <span class="bg-blue-600 text-white p-1 rounded-lg text-xs">AI</span> LuxuryEstate 3D
        </h1>
        <div class="space-x-4">
            <span class="text-xs text-green-500 font-mono animate-pulse">● AI System Active</span>
            <button class="bg-blue-600 text-white px-5 py-2 rounded-lg hover:bg-blue-700 transition">Contact Agent</button>
        </div>
    </nav>

    <div class="max-w-6xl mx-auto p-6 grid grid-cols-1 md:grid-cols-2 gap-10 mt-10">
        
        <div class="relative group bg-white rounded-2xl shadow-xl overflow-hidden border border-gray-100">
            <div class="absolute top-4 left-4 z-10 bg-black/60 backdrop-blur-md text-white px-3 py-1 rounded-full text-xs font-mono">
                AI Analysis: Structural Integrity 98%
            </div>
            
            <model-viewer 
                src="https://modelviewer.dev/shared-assets/models/Astronaut.glb" 
                camera-controls 
                auto-rotate 
                style="width: 100%; height: 500px; background-color: #f9fafb;">
            </model-viewer>
        </div>

        <div>
            <div class="inline-block bg-blue-50 text-blue-600 px-3 py-1 rounded-full text-sm font-bold mb-4">
                ✨ AI-Generated Listing
            </div>
            <h2 class="text-4xl font-bold mb-2">The Horizon Tower</h2>
            <p class="text-xl text-blue-600 font-semibold mb-6">$1,250,000 — Downtown District</p>
            
            <div class="grid grid-cols-2 gap-4 mb-8">
                <div class="bg-blue-50/50 p-4 rounded-xl border border-blue-100">
                    <p class="text-gray-500 text-xs uppercase tracking-wider">AI Yield Est.</p>
