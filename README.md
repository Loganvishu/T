"use client";
import { motion } from "framer-motion";

export default function Navbar() {
  return (
    <div className="flex justify-between items-center px-10 py-6 backdrop-blur-md bg-white/5 sticky top-0 z-50 border-b border-white/10">
      <img src="/logo.png" className="h-10" />

      <div className="space-x-8 hidden md:block">
        <a href="#services">Services</a>
        <a href="#pricing">Plans</a>
        <a href="#contact">Contact</a>
      </div>

      <a href="https://wa.me/919766198531">
        <button className="bg-green-500 px-5 py-2 rounded-lg hover:scale-105 transition">
          WhatsApp
        </button>
      </a>
    </div>
  );
}"use client";
import { motion } from "framer-motion";

export default function Hero() {
  return (
    <section className="text-center py-32 px-6">

      <motion.h1
        initial={{ opacity: 0, y: 30 }}
        animate={{ opacity: 1, y: 0 }}
        className="text-6xl font-bold leading-tight"
      >
        We Don’t Market. <br />
        <span className="text-indigo-500">We Scale Businesses 🚀</span>
      </motion.h1>

      <p className="mt-6 text-gray-400 max-w-xl mx-auto">
        Helping local businesses dominate online with premium digital strategies.
      </p>

      <div className="mt-10 flex justify-center gap-4">

        <a href="#contact">
          <button className="bg-indigo-600 px-8 py-4 rounded-xl text-lg hover:scale-105 transition">
            Get Clients Now
          </button>
        </a>

        <a href="https://wa.me/919766198531">
          <button className="border border-white/20 px-8 py-4 rounded-xl">
            WhatsApp Us
          </button>
        </a>

      </div>
    </section>
  );
}export default function Services() {
  const services = [
    "Social Media Growth",
    "Meta Ads Scaling",
    "SEO & Google Ranking",
    "Reels & Content Creation",
    "Website Development",
    "Lead Generation Systems"
  ];

  return (
    <section id="services" className="py-24 px-10">

      <h2 className="text-4xl font-bold text-center mb-16">
        Premium Services
      </h2>

      <div className="grid md:grid-cols-3 gap-8">

        {services.map((s, i) => (
          <div key={i}
            className="p-6 rounded-2xl backdrop-blur-lg bg-white/5 border border-white/10 hover:border-indigo-500 transition">

            <h3 className="text-xl">{s}</h3>

          </div>
        ))}

      </div>
    </section>
  );
}export default function Pricing() {
  return (
    <section id="pricing" className="py-24 text-center">

      <h2 className="text-4xl font-bold">Pricing Plans</h2>

      <div className="grid md:grid-cols-3 gap-10 mt-16 px-10">

        <div className="bg-white/5 p-8 rounded-2xl border border-white/10">
          <h3 className="text-xl">Starter</h3>
          <p className="text-3xl mt-4">₹5,500</p>
        </div>

        <div className="bg-indigo-600 p-10 rounded-2xl scale-105 shadow-2xl">
          <h3 className="text-xl">Booster</h3>
          <p className="text-4xl mt-4">₹9,999</p>
        </div>

        <div className="bg-white/5 p-8 rounded-2xl border border-white/10">
          <h3 className="text-xl">Elite</h3>
          <p className="text-3xl mt-4">₹15,000</p>
        </div>

      </div>
    </section>
  );export default function Pricing() {
  return (
    <section id="pricing" className="py-24 text-center">

      <h2 className="text-4xl font-bold">Pricing Plans</h2>

      <div className="grid md:grid-cols-3 gap-10 mt-16 px-10">

        <div className="bg-white/5 p-8 rounded-2xl border border-white/10">
          <h3 className="text-xl">Starter</h3>
          <p className="text-3xl mt-4">₹5,500</p>
        </div>

        <div className="bg-indigo-600 p-10 rounded-2xl scale-105 shadow-2xl">
          <h3 className="text-xl">Booster</h3>
          <p className="text-4xl mt-4">₹9,999</p>
        </div>

        <div className="bg-white/5 p-8 rounded-2xl border border-white/10">
          <h3 className="text-xl">Elite</h3>
          <p className="text-3xl mt-4">₹15,000</p>
        </div>

      </div>
    </section>
  );
}
}"use client";

import { useEffect, useState } from "react";

export default function Dashboard() {
  const [leads, setLeads] = useState([]);

  useEffect(() => {
    fetch("/api/contact")
      .then(res => res.json())
      .then(setLeads);
  }, []);

  return (
    <div className="p-10">

      <h1 className="text-4xl mb-10">Dashboard</h1>

      <div className="grid md:grid-cols-3 gap-6">

        {leads.map((lead, i) => (
          <div key={i}
            className="p-6 rounded-xl bg-white/5 border border-white/10">

            <p className="font-bold">{lead.name}</p>
            <p>{lead.phone}</p>
            <p className="text-indigo-400">{lead.service}</p>

          </div>
        ))}

      </div>
    </div>
  );
}
