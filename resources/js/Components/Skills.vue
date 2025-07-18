    <style>
        .expertise-bar {
            height: 4px;
            background: linear-gradient(90deg, #6b46c1, #ec4899);
            border-radius: 2px;
            transform-origin: left;
            transition: transform 0.3s ease;
        }

        .skill-card:hover .expertise-bar {
            transform: scaleX(1.1);
        }

        .skill-image {
            width: 40px;
            height: 40px;
            object-fit: cover;
            border-radius: 8px;
        }

        .skill-image-placeholder {
            width: 40px;
            height: 40px;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            border-radius: 8px;
            display: flex;
            align-items: center;
            justify-content: center;
            color: white;
            font-size: 12px;
            font-weight: bold;
        }
    </style>

<template>
   <section id="skills" class="py-16 px-6 relative">
    <div class="absolute inset-0 bg-black/40 backdrop-blur-sm"></div>
    <div class="max-w-4xl mx-auto relative z-10">
        <div class="text-center space-y-3 mb-12">
            <h2 class="text-3xl font-bold text-white">
                My <span class="text-purple-400">Skills</span>
            </h2>
            <div class="w-16 h-1 bg-gradient-to-r from-purple-500 to-pink-500 rounded-full mx-auto"></div>
        </div>

        <div class="grid grid-cols-2 md:grid-cols-4 gap-4">
            <!-- Java -->
            <div class="group relative skill-card">
                <div class="bg-gray-800/70 backdrop-blur-sm rounded-xl p-4 border border-gray-700/50 group-hover:border-slate-500/50 group-hover:bg-gray-700/80 transition-all duration-300 transform group-hover:scale-105 group-hover:shadow-xl group-hover:shadow-slate-500/20">
                    <div class="flex flex-col items-center space-y-3">
                        <!-- Replace src with your actual image path -->
                        <img src="images/java.png" alt="Java" class="skill-image" onerror="this.style.display='none'; this.nextElementSibling.style.display='flex';">
                        <div class="skill-image-placeholder" style="display: none;">☕</div>

                        <div class="text-center w-full">
                            <h3 class="text-sm font-semibold text-white group-hover:text-orange-400 transition-colors">Java</h3>
                            <div class="mt-2 w-full bg-gray-700 rounded-full h-1">
                                <div class="expertise-bar" style="width: 20%;"></div>
                            </div>
                            <span class="text-xs text-gray-400 mt-1">20%</span>
                        </div>
                    </div>
                </div>
            </div>

            <!-- HTML -->
            <div class="group relative skill-card">
                <div class="bg-gray-800/70 backdrop-blur-sm rounded-xl p-4 border border-gray-700/50 group-hover:border-orange-500/50 group-hover:bg-gray-700/80 transition-all duration-300 transform group-hover:scale-105 group-hover:shadow-xl group-hover:shadow-orange-500/20">
                    <div class="flex flex-col items-center space-y-3">
                        <!-- Replace src with your actual image path -->
                        <img src="images/HTML.png" alt="HTML" class="skill-image" onerror="this.style.display='none'; this.nextElementSibling.style.display='flex';">
                        <div class="skill-image-placeholder" style="display: none;">&lt;/&gt;</div>

                        <div class="text-center w-full">
                            <h3 class="text-sm font-semibold text-white group-hover:text-orange-400 transition-colors">HTML</h3>
                            <div class="mt-2 w-full bg-gray-700 rounded-full h-1">
                                <div class="expertise-bar" style="width: 75%;"></div>
                            </div>
                            <span class="text-xs text-gray-400 mt-1">75%</span>
                        </div>
                    </div>
                </div>
            </div>

            <!-- Tableau Desktop -->
            <div class="group relative skill-card">
                <div class="bg-gray-800/70 backdrop-blur-sm rounded-xl p-4 border border-gray-700/50 group-hover:border-fuchsia-500/50 group-hover:bg-gray-700/80 transition-all duration-300 transform group-hover:scale-105 group-hover:shadow-xl group-hover:shadow-fuchsia-500/20">
                    <div class="flex flex-col items-center space-y-3">
                        <!-- Replace src with your actual image path -->
                        <img src="images/Tableau.png" alt="Tableau" class="skill-image" onerror="this.style.display='none'; this.nextElementSibling.style.display='flex';">
                        <div class="skill-image-placeholder" style="display: none;">TB</div>

                        <div class="text-center w-full">
                            <h3 class="text-sm font-semibold text-white group-hover:text-blue-400 transition-colors">Tableau Desktop</h3>
                            <div class="mt-2 w-full bg-gray-700 rounded-full h-1">
                                <div class="expertise-bar" style="width: 50%;"></div>
                            </div>
                            <span class="text-xs text-gray-400 mt-1">50%</span>
                        </div>
                    </div>
                </div>
            </div>

            <!-- CSS -->
            <div class="group relative skill-card">
                <div class="bg-gray-800/70 backdrop-blur-sm rounded-xl p-4 border border-gray-700/50 group-hover:border-blue-500/50 group-hover:bg-gray-700/80 transition-all duration-300 transform group-hover:scale-105 group-hover:shadow-xl group-hover:shadow-blue-500/20">
                    <div class="flex flex-col items-center space-y-3">
                        <!-- Replace src with your actual image path -->
                        <img src="images/CSS.png" alt="C#" class="skill-image" onerror="this.style.display='none'; this.nextElementSibling.style.display='flex';">
                        <div class="skill-image-placeholder" style="display: none;">C#</div>

                        <div class="text-center w-full">
                            <h3 class="text-sm font-semibold text-white group-hover:text-purple-400 transition-colors">CSS</h3>
                            <div class="mt-2 w-full bg-gray-700 rounded-full h-1">
                                <div class="expertise-bar" style="width: 75%;"></div>
                            </div>
                            <span class="text-xs text-gray-400 mt-1">75%</span>
                        </div>
                    </div>
                </div>
            </div>

            <!-- Power BI -->
            <div class="group relative skill-card">
                <div class="bg-gray-800/70 backdrop-blur-sm rounded-xl p-4 border border-gray-700/50 group-hover:border-yellow-500/50 group-hover:bg-gray-700/80 transition-all duration-300 transform group-hover:scale-105 group-hover:shadow-xl group-hover:shadow-yellow-500/20">
                    <div class="flex flex-col items-center space-y-3">
                        <!-- Replace src with your actual image path -->
                        <img src="images/PowerBI.png" alt="C#" class="skill-image" onerror="this.style.display='none'; this.nextElementSibling.style.display='flex';">
                        <div class="skill-image-placeholder" style="display: none;">C#</div>

                        <div class="text-center w-full">
                            <h3 class="text-sm font-semibold text-white group-hover:text-purple-400 transition-colors">Microsoft Power BI</h3>
                            <div class="mt-2 w-full bg-gray-700 rounded-full h-1">
                                <div class="expertise-bar" style="width: 10%;"></div>
                            </div>
                            <span class="text-xs text-gray-400 mt-1">10%</span>
                        </div>
                    </div>
                </div>
            </div>

            <!-- Flutterflow -->
            <div class="group relative skill-card">
                <div class="bg-gray-800/70 backdrop-blur-sm rounded-xl p-4 border border-gray-700/50 group-hover:border-indigo-500/50 group-hover:bg-gray-700/80 transition-all duration-300 transform group-hover:scale-105 group-hover:shadow-xl group-hover:shadow-indigo-500/20">
                    <div class="flex flex-col items-center space-y-3">
                        <!-- Replace src with your actual image path -->
                        <img src="images/Flutterflow.png" alt="C#" class="skill-image" onerror="this.style.display='none'; this.nextElementSibling.style.display='flex';">
                        <div class="skill-image-placeholder" style="display: none;">C#</div>

                        <div class="text-center w-full">
                            <h3 class="text-sm font-semibold text-white group-hover:text-purple-400 transition-colors">Flutterflow</h3>
                            <div class="mt-2 w-full bg-gray-700 rounded-full h-1">
                                <div class="expertise-bar" style="width: 90%;"></div>
                            </div>
                            <span class="text-xs text-gray-400 mt-1">90%</span>
                        </div>
                    </div>
                </div>
            </div>

            <!-- Xampp -->
            <div class="group relative skill-card">
                <div class="bg-gray-800/70 backdrop-blur-sm rounded-xl p-4 border border-gray-700/50 group-hover:border-amber-500/50 group-hover:bg-gray-700/80 transition-all duration-300 transform group-hover:scale-105 group-hover:shadow-xl group-hover:shadow-amber-500/20">
                    <div class="flex flex-col items-center space-y-3">
                        <!-- Replace src with your actual image path -->
                        <img src="images/Xampp.png" alt="C#" class="skill-image" onerror="this.style.display='none'; this.nextElementSibling.style.display='flex';">
                        <div class="skill-image-placeholder" style="display: none;">C#</div>

                        <div class="text-center w-full">
                            <h3 class="text-sm font-semibold text-white group-hover:text-purple-400 transition-colors">Xampp</h3>
                            <div class="mt-2 w-full bg-gray-700 rounded-full h-1">
                                <div class="expertise-bar" style="width: 45%;"></div>
                            </div>
                            <span class="text-xs text-gray-400 mt-1">45%</span>
                        </div>
                    </div>
                </div>
            </div>

            <!-- Laragon -->
            <div class="group relative skill-card">
                <div class="bg-gray-800/70 backdrop-blur-sm rounded-xl p-4 border border-gray-700/50 group-hover:border-cyan-500/50 group-hover:bg-gray-700/80 transition-all duration-300 transform group-hover:scale-105 group-hover:shadow-xl group-hover:shadow-cyan-500/20">
                    <div class="flex flex-col items-center space-y-3">
                        <!-- Replace src with your actual image path -->
                        <img src="images/Laragon.png" alt="C#" class="skill-image" onerror="this.style.display='none'; this.nextElementSibling.style.display='flex';">
                        <div class="skill-image-placeholder" style="display: none;">C#</div>

                        <div class="text-center w-full">
                            <h3 class="text-sm font-semibold text-white group-hover:text-purple-400 transition-colors">Laragon</h3>
                            <div class="mt-2 w-full bg-gray-700 rounded-full h-1">
                                <div class="expertise-bar" style="width: 30%;"></div>
                            </div>
                            <span class="text-xs text-gray-400 mt-1">30%</span>
                        </div>
                    </div>
                </div>
            </div>

            <!-- Laravel -->
            <div class="group relative skill-card">
                <div class="bg-gray-800/70 backdrop-blur-sm rounded-xl p-4 border border-gray-700/50 group-hover:border-red-500/50 group-hover:bg-gray-700/80 transition-all duration-300 transform group-hover:scale-105 group-hover:shadow-xl group-hover:shadow-red-500/20">
                    <div class="flex flex-col items-center space-y-3">
                        <!-- Replace src with your actual image path -->
                        <img src="images/Laravel.png" alt="C#" class="skill-image" onerror="this.style.display='none'; this.nextElementSibling.style.display='flex';">
                        <div class="skill-image-placeholder" style="display: none;">C#</div>

                        <div class="text-center w-full">
                            <h3 class="text-sm font-semibold text-white group-hover:text-purple-400 transition-colors">Laravel</h3>
                            <div class="mt-2 w-full bg-gray-700 rounded-full h-1">
                                <div class="expertise-bar" style="width: 70%;"></div>
                            </div>
                            <span class="text-xs text-gray-400 mt-1">70%</span>
                        </div>
                    </div>
                </div>
            </div>

            <!-- CI3 -->
            <div class="group relative skill-card">
                <div class="bg-gray-800/70 backdrop-blur-sm rounded-xl p-4 border border-gray-700/50 group-hover:border-orange-500/50 group-hover:bg-gray-700/80 transition-all duration-300 transform group-hover:scale-105 group-hover:shadow-xl group-hover:shadow-orange-500/20">
                    <div class="flex flex-col items-center space-y-3">
                        <!-- Replace src with your actual image path -->
                        <img src="images/CodeIgniter3.png" alt="C#" class="skill-image" onerror="this.style.display='none'; this.nextElementSibling.style.display='flex';">
                        <div class="skill-image-placeholder" style="display: none;">C#</div>

                        <div class="text-center w-full">
                            <h3 class="text-sm font-semibold text-white group-hover:text-purple-400 transition-colors">CodeIgniter 3</h3>
                            <div class="mt-2 w-full bg-gray-700 rounded-full h-1">
                                <div class="expertise-bar" style="width: 60%;"></div>
                            </div>
                            <span class="text-xs text-gray-400 mt-1">60%</span>
                        </div>
                    </div>
                </div>
            </div>

            <!-- Firebase -->
            <div class="group relative skill-card">
                <div class="bg-gray-800/70 backdrop-blur-sm rounded-xl p-4 border border-gray-700/50 group-hover:border-amber-500/50 group-hover:bg-gray-700/80 transition-all duration-300 transform group-hover:scale-105 group-hover:shadow-xl group-hover:shadow-amber-500/20">
                    <div class="flex flex-col items-center space-y-3">
                        <!-- Replace src with your actual image path -->
                        <img src="images/Firebase.png" alt="C#" class="skill-image" onerror="this.style.display='none'; this.nextElementSibling.style.display='flex';">
                        <div class="skill-image-placeholder" style="display: none;">C#</div>

                        <div class="text-center w-full">
                            <h3 class="text-sm font-semibold text-white group-hover:text-purple-400 transition-colors">Firebase</h3>
                            <div class="mt-2 w-full bg-gray-700 rounded-full h-1">
                                <div class="expertise-bar" style="width: 55%;"></div>
                            </div>
                            <span class="text-xs text-gray-400 mt-1">55%</span>
                        </div>
                    </div>
                </div>
            </div>

            <!-- Mysql -->
            <div class="group relative skill-card">
                <div class="bg-gray-800/70 backdrop-blur-sm rounded-xl p-4 border border-gray-700/50 group-hover:border-slate-500/50 group-hover:bg-gray-700/80 transition-all duration-300 transform group-hover:scale-105 group-hover:shadow-xl group-hover:shadow-slate-500/20">
                    <div class="flex flex-col items-center space-y-3">
                        <!-- Replace src with your actual image path -->
                        <img src="images/MySQL.png" alt="C#" class="skill-image" onerror="this.style.display='none'; this.nextElementSibling.style.display='flex';">
                        <div class="skill-image-placeholder" style="display: none;">C#</div>

                        <div class="text-center w-full">
                            <h3 class="text-sm font-semibold text-white group-hover:text-purple-400 transition-colors">MySQL</h3>
                            <div class="mt-2 w-full bg-gray-700 rounded-full h-1">
                                <div class="expertise-bar" style="width: 60%;"></div>
                            </div>
                            <span class="text-xs text-gray-400 mt-1">60%</span>
                        </div>
                    </div>
                </div>
            </div>

            <!-- Git -->
            <div class="group relative skill-card">
                <div class="bg-gray-800/70 backdrop-blur-sm rounded-xl p-4 border border-gray-700/50 group-hover:border-red-500/50 group-hover:bg-gray-700/80 transition-all duration-300 transform group-hover:scale-105 group-hover:shadow-xl group-hover:shadow-red-500/20">
                    <div class="flex flex-col items-center space-y-3">
                        <!-- Replace src with your actual image path -->
                        <img src="images/Git.png" alt="C#" class="skill-image" onerror="this.style.display='none'; this.nextElementSibling.style.display='flex';">
                        <div class="skill-image-placeholder" style="display: none;">C#</div>

                        <div class="text-center w-full">
                            <h3 class="text-sm font-semibold text-white group-hover:text-purple-400 transition-colors">Git</h3>
                            <div class="mt-2 w-full bg-gray-700 rounded-full h-1">
                                <div class="expertise-bar" style="width: 35%;"></div>
                            </div>
                            <span class="text-xs text-gray-400 mt-1">35%</span>
                        </div>
                    </div>
                </div>
            </div>

            <!-- Microsoft excel -->
            <div class="group relative skill-card">
                <div class="bg-gray-800/70 backdrop-blur-sm rounded-xl p-4 border border-gray-700/50 group-hover:border-emerald-500/50 group-hover:bg-gray-700/80 transition-all duration-300 transform group-hover:scale-105 group-hover:shadow-xl group-hover:shadow-emerald-500/20">
                    <div class="flex flex-col items-center space-y-3">
                        <!-- Replace src with your actual image path -->
                        <img src="images/Excel.png" alt="C#" class="skill-image" onerror="this.style.display='none'; this.nextElementSibling.style.display='flex';">
                        <div class="skill-image-placeholder" style="display: none;">C#</div>

                        <div class="text-center w-full">
                            <h3 class="text-sm font-semibold text-white group-hover:text-purple-400 transition-colors">Microsoft Excel</h3>
                            <div class="mt-2 w-full bg-gray-700 rounded-full h-1">
                                <div class="expertise-bar" style="width: 50%;"></div>
                            </div>
                            <span class="text-xs text-gray-400 mt-1">50%</span>
                        </div>
                    </div>
                </div>
            </div>

            <!-- Figma -->
            <div class="group relative skill-card">
                <div class="bg-gray-800/70 backdrop-blur-sm rounded-xl p-4 border border-gray-700/50 group-hover:border-green-500/50 group-hover:bg-gray-700/80 transition-all duration-300 transform group-hover:scale-105 group-hover:shadow-xl group-hover:shadow-green-500/20">
                    <div class="flex flex-col items-center space-y-3">
                        <!-- Replace src with your actual image path -->
                        <img src="images/Figma.png" alt="C#" class="skill-image" onerror="this.style.display='none'; this.nextElementSibling.style.display='flex';">
                        <div class="skill-image-placeholder" style="display: none;">C#</div>

                        <div class="text-center w-full">
                            <h3 class="text-sm font-semibold text-white group-hover:text-purple-400 transition-colors">Figma</h3>
                            <div class="mt-2 w-full bg-gray-700 rounded-full h-1">
                                <div class="expertise-bar" style="width: 90%;"></div>
                            </div>
                            <span class="text-xs text-gray-400 mt-1">90%</span>
                        </div>
                    </div>
                </div>
            </div>

            <!-- Vue.js -->
            <div class="group relative skill-card">
                <div class="bg-gray-800/70 backdrop-blur-sm rounded-xl p-4 border border-gray-700/50 group-hover:border-lime-500/50 group-hover:bg-gray-700/80 transition-all duration-300 transform group-hover:scale-105 group-hover:shadow-xl group-hover:shadow-lime-500/20">
                    <div class="flex flex-col items-center space-y-3">
                        <!-- Replace src with your actual image path -->
                        <img src="images/Vuejs.png" alt="C#" class="skill-image" onerror="this.style.display='none'; this.nextElementSibling.style.display='flex';">
                        <div class="skill-image-placeholder" style="display: none;">C#</div>

                        <div class="text-center w-full">
                            <h3 class="text-sm font-semibold text-white group-hover:text-purple-400 transition-colors">Vue.js</h3>
                            <div class="mt-2 w-full bg-gray-700 rounded-full h-1">
                                <div class="expertise-bar" style="width: 55%;"></div>
                            </div>
                            <span class="text-xs text-gray-400 mt-1">55%</span>
                        </div>
                    </div>
                </div>
            </div>

            <!-- Adobe XD -->
            <div class="group relative skill-card">
                <div class="bg-gray-800/70 backdrop-blur-sm rounded-xl p-4 border border-gray-700/50 group-hover:border-pink-500/50 group-hover:bg-gray-700/80 transition-all duration-300 transform group-hover:scale-105 group-hover:shadow-xl group-hover:shadow-pink-500/20">
                    <div class="flex flex-col items-center space-y-3">
                        <!-- Replace src with your actual image path -->
                        <img src="images/AdobeXD.png" alt="C#" class="skill-image" onerror="this.style.display='none'; this.nextElementSibling.style.display='flex';">
                        <div class="skill-image-placeholder" style="display: none;">C#</div>

                        <div class="text-center w-full">
                            <h3 class="text-sm font-semibold text-white group-hover:text-purple-400 transition-colors">Adobe XD</h3>
                            <div class="mt-2 w-full bg-gray-700 rounded-full h-1">
                                <div class="expertise-bar" style="width: 35%;"></div>
                            </div>
                            <span class="text-xs text-gray-400 mt-1">35%</span>
                        </div>
                    </div>
                </div>
            </div>

            <!-- Javascript -->
            <div class="group relative skill-card">
                <div class="bg-gray-800/70 backdrop-blur-sm rounded-xl p-4 border border-gray-700/50 group-hover:border-yellow-500/50 group-hover:bg-gray-700/80 transition-all duration-300 transform group-hover:scale-105 group-hover:shadow-xl group-hover:shadow-yellow-500/20">
                    <div class="flex flex-col items-center space-y-3">
                        <!-- Replace src with your actual image path -->
                        <img src="images/Javascript.png" alt="C#" class="skill-image" onerror="this.style.display='none'; this.nextElementSibling.style.display='flex';">
                        <div class="skill-image-placeholder" style="display: none;">C#</div>

                        <div class="text-center w-full">
                            <h3 class="text-sm font-semibold text-white group-hover:text-purple-400 transition-colors">Javascript</h3>
                            <div class="mt-2 w-full bg-gray-700 rounded-full h-1">
                                <div class="expertise-bar" style="width: 55%;"></div>
                            </div>
                            <span class="text-xs text-gray-400 mt-1">55%</span>
                        </div>
                    </div>
                </div>
            </div>

            <!-- Android Studio -->
            <div class="group relative skill-card">
                <div class="bg-gray-800/70 backdrop-blur-sm rounded-xl p-4 border border-gray-700/50 group-hover:border-teal-500/50 group-hover:bg-gray-700/80 transition-all duration-300 transform group-hover:scale-105 group-hover:shadow-xl group-hover:shadow-teal-500/20">
                    <div class="flex flex-col items-center space-y-3">
                        <!-- Replace src with your actual image path -->
                        <img src="images/AndroidStudio.png" alt="C#" class="skill-image" onerror="this.style.display='none'; this.nextElementSibling.style.display='flex';">
                        <div class="skill-image-placeholder" style="display: none;">C#</div>

                        <div class="text-center w-full">
                            <h3 class="text-sm font-semibold text-white group-hover:text-purple-400 transition-colors">Android Studio</h3>
                            <div class="mt-2 w-full bg-gray-700 rounded-full h-1">
                                <div class="expertise-bar" style="width: 60%;"></div>
                            </div>
                            <span class="text-xs text-gray-400 mt-1">60%</span>
                        </div>
                    </div>
                </div>
            </div>

            <!-- Unity -->
            <div class="group relative skill-card">
                <div class="bg-gray-800/70 backdrop-blur-sm rounded-xl p-4 border border-gray-700/50 group-hover:border-purple-500/50 group-hover:bg-gray-700/80 transition-all duration-300 transform group-hover:scale-105 group-hover:shadow-xl group-hover:shadow-purple-500/20">
                    <div class="flex flex-col items-center space-y-3">
                        <!-- Replace src with your actual image path -->
                        <img src="images/Unity.png" alt="C#" class="skill-image" onerror="this.style.display='none'; this.nextElementSibling.style.display='flex';">
                        <div class="skill-image-placeholder" style="display: none;">C#</div>

                        <div class="text-center w-full">
                            <h3 class="text-sm font-semibold text-white group-hover:text-purple-400 transition-colors">Unity</h3>
                            <div class="mt-2 w-full bg-gray-700 rounded-full h-1">
                                <div class="expertise-bar" style="width: 75%;"></div>
                            </div>
                            <span class="text-xs text-gray-400 mt-1">75%</span>
                        </div>
                    </div>
                </div>
            </div>

            <!-- vscode -->
            <div class="group relative skill-card">
                <div class="bg-gray-800/70 backdrop-blur-sm rounded-xl p-4 border border-gray-700/50 group-hover:border-teal-500/50 group-hover:bg-gray-700/80 transition-all duration-300 transform group-hover:scale-105 group-hover:shadow-xl group-hover:shadow-teal-500/20">
                    <div class="flex flex-col items-center space-y-3">
                        <!-- Replace src with your actual image path -->
                        <img src="images/vscode.png" alt="C#" class="skill-image" onerror="this.style.display='none'; this.nextElementSibling.style.display='flex';">
                        <div class="skill-image-placeholder" style="display: none;">C#</div>

                        <div class="text-center w-full">
                            <h3 class="text-sm font-semibold text-white group-hover:text-purple-400 transition-colors">Visual Studio Code</h3>
                            <div class="mt-2 w-full bg-gray-700 rounded-full h-1">
                                <div class="expertise-bar" style="width: 80%;"></div>
                            </div>
                            <span class="text-xs text-gray-400 mt-1">80%</span>
                        </div>
                    </div>
                </div>
            </div>

            <!-- Powerpoint -->
            <div class="group relative skill-card">
                <div class="bg-gray-800/70 backdrop-blur-sm rounded-xl p-4 border border-gray-700/50 group-hover:border-amber-500/50 group-hover:bg-gray-700/80 transition-all duration-300 transform group-hover:scale-105 group-hover:shadow-xl group-hover:shadow-amber-500/20">
                    <div class="flex flex-col items-center space-y-3">
                        <!-- Replace src with your actual image path -->
                        <img src="images/Powerpoint.png" alt="C#" class="skill-image" onerror="this.style.display='none'; this.nextElementSibling.style.display='flex';">
                        <div class="skill-image-placeholder" style="display: none;">C#</div>

                        <div class="text-center w-full">
                            <h3 class="text-sm font-semibold text-white group-hover:text-purple-400 transition-colors">Microsoft Powerpoint</h3>
                            <div class="mt-2 w-full bg-gray-700 rounded-full h-1">
                                <div class="expertise-bar" style="width: 85%;"></div>
                            </div>
                            <span class="text-xs text-gray-400 mt-1">85%</span>
                        </div>
                    </div>
                </div>
            </div>

            <!-- Word -->
            <div class="group relative skill-card">
                <div class="bg-gray-800/70 backdrop-blur-sm rounded-xl p-4 border border-gray-700/50 group-hover:border-blue-500/50 group-hover:bg-gray-700/80 transition-all duration-300 transform group-hover:scale-105 group-hover:shadow-xl group-hover:shadow-blue-500/20">
                    <div class="flex flex-col items-center space-y-3">
                        <!-- Replace src with your actual image path -->
                        <img src="images/Word.png" alt="C#" class="skill-image" onerror="this.style.display='none'; this.nextElementSibling.style.display='flex';">
                        <div class="skill-image-placeholder" style="display: none;">C#</div>

                        <div class="text-center w-full">
                            <h3 class="text-sm font-semibold text-white group-hover:text-purple-400 transition-colors">Microsoft Word</h3>
                            <div class="mt-2 w-full bg-gray-700 rounded-full h-1">
                                <div class="expertise-bar" style="width: 90%;"></div>
                            </div>
                            <span class="text-xs text-gray-400 mt-1">90%</span>
                        </div>
                    </div>
                </div>
            </div>

            <!-- C -->
            <div class="group relative skill-card">
                <div class="bg-gray-800/70 backdrop-blur-sm rounded-xl p-4 border border-gray-700/50 group-hover:border-purple-500/50 group-hover:bg-gray-700/80 transition-all duration-300 transform group-hover:scale-105 group-hover:shadow-xl group-hover:shadow-purple-500/20">
                    <div class="flex flex-col items-center space-y-3">
                        <!-- Replace src with your actual image path -->
                        <img src="images/C.png" alt="C#" class="skill-image" onerror="this.style.display='none'; this.nextElementSibling.style.display='flex';">
                        <div class="skill-image-placeholder" style="display: none;">C#</div>

                        <div class="text-center w-full">
                            <h3 class="text-sm font-semibold text-white group-hover:text-purple-400 transition-colors">C</h3>
                            <div class="mt-2 w-full bg-gray-700 rounded-full h-1">
                                <div class="expertise-bar" style="width: 10%;"></div>
                            </div>
                            <span class="text-xs text-gray-400 mt-1">10%</span>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>
</section>
</template>
