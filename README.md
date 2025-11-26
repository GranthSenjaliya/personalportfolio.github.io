# personalportfolio.github.io
// Portfolio.jsx
// Single-file React component for a modern portfolio like https://parthkp126.github.io/protfolio/
// Uses Tailwind CSS for styling and framer-motion for simple animations.
// To preview locally:
// 1) Create a new React app (Vite or CRA).
// 2) Install Tailwind and framer-motion. Example (Vite):
//    npm create vite@latest my-portfolio --template react
//    cd my-portfolio
//    npm install
//    npm install framer-motion
//    Follow Tailwind docs to install Tailwind CSS in the project.
// 3) Place this file in src/components/Portfolio.jsx and import it in App.jsx.

import React from "react";
import { motion } from "framer-motion";

export default function Portfolio() {
  const projects = [
    {
      title: "Project One",
      desc: "Short description of project one — what it does and why it matters.",
      url: "#",
      tags: ["React", "Tailwind", "API"],
    },
    {
      title: "Project Two",
      desc: "Short description of project two — what it does and why it matters.",
      url: "#",
      tags: ["ESP32", "IoT", "C++"],
    },
    {
      title: "Project Three",
      desc: "Short description of project three — mobile or web app demo.",
      url: "#",
      tags: ["Python", "ML"],
    },
  ];

  return (
    <div className="min-h-screen bg-gray-50 text-gray-900 antialiased">
      <header className="max-w-5xl mx-auto p-6 flex items-center justify-between">
        <div className="flex items-center gap-3">
          <div className="w-12 h-12 rounded-full bg-gradient-to-br from-indigo-500 to-pink-500 flex items-center justify-center text-white font-bold">GS</div>
          <div>
            <div className="text-lg font-semibold">Granth Senjaliya</div>
            <div className="text-sm text-gray-500">Embedded systems & web developer</div>
          </div>
        </div>
        <nav className="hidden md:flex gap-6 text-sm">
          <a href="#about" className="hover:text-indigo-600">About</a>
          <a href="#projects" className="hover:text-indigo-600">Projects</a>
          <a href="#skills" className="hover:text-indigo-600">Skills</a>
          <a href="#contact" className="hover:text-indigo-600">Contact</a>
        </nav>
      </header>

      <main className="max-w-5xl mx-auto p-6">
        <section className="grid md:grid-cols-2 gap-8 items-center mt-6">
          <motion.div
            initial={{ opacity: 0, y: 10 }}
            animate={{ opacity: 1, y: 0 }}
            transition={{ duration: 0.6 }}
          >
            <h1 className="text-4xl md:text-5xl font-extrabold leading-tight">
              Hi, I’m <span className="text-indigo-600">Granth Senjaliya</span>
            </h1>
            <p className="mt-4 text-gray-600 max-w-xl">
              I build embedded systems, IoT solutions, and polished web experiences. I enjoy
              turning ideas into working prototypes and production-ready applications.
            </p>

            <div className="mt-6 flex gap-3">
              <a href="#projects" className="inline-flex items-center px-4 py-2 rounded-lg bg-indigo-600 text-white">See projects</a>
              <a href="#contact" className="inline-flex items-center px-4 py-2 rounded-lg border border-gray-200">Contact me</a>
            </div>

            <div className="mt-8 flex gap-4 text-gray-500">
              <a href="https://github.com/granthsenjaliya" aria-label="GitHub" title="GitHub">GitHub</a>
              <a href="https://linkedin.com/in/granthsenjaliya" aria-label="LinkedIn" title="LinkedIn">LinkedIn</a>
              <a href="#" aria-label="Twitter" title="Twitter">Twitter</a>
            </div>
          </motion.div>

          <motion.div
            className="order-first md:order-last"
            initial={{ opacity: 0, scale: 0.98 }}
            animate={{ opacity: 1, scale: 1 }}
            transition={{ duration: 0.6 }}
          >
            <div className="w-full rounded-2xl overflow-hidden shadow-lg bg-white">
              <img src="https://source.unsplash.com/collection/895539/800x600" alt="hero" className="w-full h-64 object-cover" />
            </div>
          </motion.div>
        </section>

        <section id="about" className="mt-16 bg-white rounded-2xl p-6 shadow-sm">
          <h2 className="text-2xl font-semibold">About me</h2>
          <p className="mt-4 text-gray-600">
            I'm a developer with experience in embedded firmware (ESP32/Arduino), sensors, and full-stack web
            development. I love building practical projects that solve real problems — from animal-deterrent IoT systems
            to responsive web dashboards.
          </p>

          <div className="mt-4 grid sm:grid-cols-2 gap-4">
            <div>
              <h3 className="font-medium">Location</h3>
              <p className="text-gray-500 text-sm">India</p>
            </div>
            <div>
              <h3 className="font-medium">Availability</h3>
              <p className="text-gray-500 text-sm">Open to freelance and collaborations</p>
            </div>
          </div>
        </section>

        <section id="projects" className="mt-10">
          <h2 className="text-2xl font-semibold">Selected projects</h2>
          <div className="mt-6 grid sm:grid-cols-2 gap-6">
            {projects.map((p, i) => (
              <motion.a
                key={i}
                href={p.url}
                className="block bg-white rounded-xl p-5 shadow hover:shadow-md transition-shadow"
                whileHover={{ y: -4 }}
              >
                <div className="flex items-start justify-between gap-4">
                  <div>
                    <h3 className="text-lg font-semibold">{p.title}</h3>
                    <p className="mt-2 text-gray-600 text-sm">{p.desc}</p>
                  </div>
                </div>

                <div className="mt-4 flex gap-2 flex-wrap text-xs">
                  {p.tags.map((t) => (
                    <span key={t} className="px-2 py-1 rounded bg-gray-100">{t}</span>
                  ))}
                </div>
              </motion.a>
            ))}
          </div>
        </section>

        <section id="skills" className="mt-10 bg-white p-6 rounded-2xl shadow-sm">
          <h2 className="text-2xl font-semibold">Skills</h2>
          <div className="mt-4 grid sm:grid-cols-3 gap-4">
            <div>
              <h4 className="font-medium">Embedded</h4>
              <p className="text-sm text-gray-500">ESP32, Arduino, C/C++, Sensors, PCB basics</p>
            </div>
            <div>
              <h4 className="font-medium">Web</h4>
              <p className="text-sm text-gray-500">React, Tailwind, Node.js, REST APIs</p>
            </div>
            <div>
              <h4 className="font-medium">Tools</h4>
              <p className="text-sm text-gray-500">Git, VSCode, Linux, Fritzing</p>
            </div>
          </div>
        </section>

        <section id="contact" className="mt-10">
          <div className="bg-gradient-to-r from-indigo-50 to-pink-50 p-6 rounded-2xl">
            <h2 className="text-2xl font-semibold">Get in touch</h2>
            <p className="mt-2 text-gray-600">Send me an email or connect on LinkedIn.</p>

            <div className="mt-4 flex gap-3">
              <a href="mailto:granth@example.com" className="inline-flex items-center px-4 py-2 rounded-lg bg-indigo-600 text-white">Email me</a>
              <a href="https://linkedin.com/in/granthsenjaliya" className="inline-flex items-center px-4 py-2 rounded-lg border">LinkedIn</a>
            </div>
          </div>
        </section>

        <footer className="mt-12 text-center text-sm text-gray-500 pb-12">
          © {new Date().getFullYear()} Granth Senjaliya • Built with ❤
        </footer>
      </main>
    </div>
  );
}
