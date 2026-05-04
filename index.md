import Image from 'next/image';
import useIntersectionObserver from '../hooks/useIntersectionObserver';

const HeroSection = () => {
  const { ref, inView } = useIntersectionObserver();

  return (
    <section className="relative h-screen bg-cover bg-center flex items-center justify-center text-white" style={{ backgroundImage: `url('/hero-image.jpg')` }}>
      <div ref={ref} className={`max-w-2xl px-4 sm:px-6 md:px-8 lg:px-10 ${inView ? 'animate-fade-in' : ''}`}>
        <h1 className="text-5xl font-bold mb-4">התקנה, תחזוקה וניקיון</h1>
        <p className="text-xl mb-8">שירות אמין ומחיר הוגן</p>
        <a href="tel:0523172392" className="inline-block px-6 py-3 text-lg font-semibold bg-white text-black rounded-full hover:bg-gray-100 transition duration-300 ease-in-out">
          התקשר עכשיו
        </a>
      </div>
    </section>
  );
};

export default HeroSection;
import { motion } from 'framer-motion';
import useIntersectionObserver from '../hooks/useIntersectionObserver';

const services = [
  {
    title: 'ремонт',
    description: 'תחזוקה של כל סוגי המזגנים.',
    icon: '/icons/repair.svg'
  },
  {
    title: 'תקנה',
    description: 'התקנה מהירה ויעילה.',
    icon: '/icons/installation.svg'
  },
  {
    title: 'ניקיון',
    description: 'ניקוי מזגנים.',
    icon: '/icons/cleaning.svg'
  }
];

const ServicesSection = () => {
  const { ref, inView } = useIntersectionObserver();

  return (
    <section className="py-20" ref={ref}>
      <div className="container mx-auto px-4 sm:px-6 md:px-8 lg:px-10">
        <h2 className="text-3xl font-bold text-center mb-8">השירותים שלנו</h2>
        <motion.div className="grid grid-cols-1 md:grid-cols-3 gap-8" style={{ opacity: inView ? 1 : 0, transition: 'opacity 0.5s' }}>
          {services.map((service, index) => (
            <div key={index} className="bg-white p-6 rounded-lg shadow-md flex items-center space-x-4">
              <Image src={service.icon} alt={service.title} width={50} height={50} />
              <div>
                <h3 className="text-xl font-bold">{service.title}</h3>
                <p>{service.description}</p>
              </div>
            </div>
          ))}
        </motion.div>
      </div>
    </section>
  );
};

export default ServicesSection;
import { motion } from 'framer-motion';
import useIntersectionObserver from '../hooks/useIntersectionObserver';

const features = [
  {
    title: 'שירות מהיר',
    description: 'úngיש ויעיל.',
    icon: '/icons/fast.svg'
  },
  {
    title: 'מחיר נוח',
    description: 'כל כיס.',
    icon: '/icons/pricing.svg'
  },
  {
    title: 'עבודהПрофессионаלית',
    description: 'איכות גבוהה.',
    icon: '/icons/professional.svg'
  },
  {
    title: 'זמינות 24/7',
    description: 'יום כל יום.',
    icon: '/icons/availability.svg'
  }
];

const WhyChooseUs = () => {
  const { ref, inView } = useIntersectionObserver();

  return (
    <section className="py-20" ref={ref}>
      <div className="container mx-auto px-4 sm:px-6 md:px-8 lg:px-10">
        <h2 className="text-3xl font-bold text-center mb-8">ทำไม לבחור בنا?</h2>
        <motion.div className="grid grid-cols-1 md:grid-cols-2 gap-8" style={{ opacity: inView ? 1 : 0, transition: 'opacity 0.5s' }}>
          {features.map((feature, index) => (
            <div key={index} className="bg-white p-6 rounded-lg shadow-md flex items-center space-x-4">
              <Image src={feature.icon} alt={feature.title} width={50} height={50} />
              <div>
                <h3 className="text-xl font-bold">{feature.title}</h3>
                <p>{feature.description}</p>
              </div>
            </div>
          ))}
        </motion.div>
      </div>
    </section>
  );
};

export default WhyChooseUs;
import { motion } from 'framer-motion';
import useIntersectionObserver from '../hooks/useIntersectionObserver';

const reviews = [
  {
    text: 'שירות אישי ומעולה! קיבלתי מענה תוך זמן קצר ואיתרו את התקלה במהרה, בנוסף גם ביקשו מחיר הוגן.',
    author: 'omer'
  },
  {
    text: 'התקינו לי מזגן טורנדו חדש באותו היום שירות מהיר ומחיר מעולה!',
    author: 'david'
  },
  {
    text: 'שירות מקצועי ויעיל! מחיר נוח לכל כיס, תענוג!',
    author: 'shira'
  }
];

const ReviewsSection = () => {
  const { ref, inView } = useIntersectionObserver();

  return (
    <section className="py-20" ref={ref}>
      <div className="container mx-auto px-4 sm:px-6 md:px-8 lg:px-10">
        <h2 className="text-3xl font-bold text-center mb-8">הآراء שלנו</h2>
        <motion.div className="carousel" style={{ opacity: inView ? 1 : 0, transition: 'opacity 0.5s' }}>
          {reviews.map((review, index) => (
            <div key={index} className="bg-white p-6 rounded-lg shadow-md mb-4">
              <p>{review.text}</p>
              <p className="text-sm text-gray-500 mt-2">{review.author}</p>
            </div>
          ))}
        </motion.div>
      </div>
    </section>
  );
};

export default ReviewsSection;
import { motion } from 'framer-motion';
import useIntersectionObserver from '../hooks/useIntersectionObserver';

const ContactSection = () => {
  const { ref, inView } = useIntersectionObserver();

  return (
    <section className="py-20" ref={ref}>
      <div className="container mx-auto px-4 sm:px-6 md:px-8 lg:px-10">
        <h2 className="text-3xl font-bold text-center mb-8">יצירת קשר</h2>
        <motion.div className="flex flex-col space-y-4" style={{ opacity: inView ? 1 : 0, transition: 'opacity 0.5s' }}>
          <p>כתובת: גיורא 10, קריית ביאליק</p>
          <a href="tel:0523172392" className="text-blue-500">טלפון: 052-317-2392</a>
          <div className="w-full h-screen">
            <iframe
              src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d3381.6400650817335!2d35.09752291547791!3d32.06784798113058!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x151d5b7a1c0e92b3%3A0xf0e0b0b0b0b0b0b0!2z4YKj4YOo4YOzIOSw4YOn4YKi4YOl4YOsIC0g4YKh4YOm4YOv4YKs4YOm!5e0!3m2!1siw!2sil!4v1633076800000!5m2!1siw!2sil"
              width="100%"
              height="450"
              style={{ border: 0 }}
              allowFullScreen
              loading="lazy"
            ></iframe>
          </div>
        </motion.div>
      </div>
    </section>
  );
};

export default ContactSection;
import { motion } from 'framer-motion';

const FloatingButton = () => {
  return (
    <motion.a
      href="tel:0523172392"
      className="fixed bottom-4 right-4 z-10 p-4 bg-blue-500 text-white rounded-full shadow-lg hover:bg-blue-600 transition duration-300 ease-in-out"
      whileHover={{ scale: 1.1 }}
    >
      <svg xmlns="http://www.w3.org/2000/svg" className="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor">
        <path strokeLinecap="round" strokeLinejoin="round" strokeWidth={2} d="M3 5a1 1 0 011-1h12a1 1 0 110 2H4a1 1 0 01-1-1z"></path>
        <path strokeLinecap="round" strokeLinejoin="round" strokeWidth={2} d="M3 10a1 1 0 011-1h4a1 1 0 010 2H4a1 1 0 01-1-1z"></path>
        <path strokeLinecap="round" strokeLinejoin="round" strokeWidth={2} d="M3 15a1 1 0 011-1h9a1 1 0 110 2H4a1 1 0 01-1-1z"></path>
      </svg>
    </motion.a>
  );
};

export default FloatingButton;
import Head from 'next/head';
import { AnimatePresence } from 'framer-motion';

const Layout = ({ children }) => {
  return (
    <div className="bg-gray-100 min-h-screen">
      <Head>
        <title>א.ב. פתרונות מיזוג</title>
        <meta name="description" content="תקנה, תחזוקה וניקיון של כל סוגי המזגנים." />
        <link rel="icon" href="/favicon.ico" />
      </Head>

      <main className="flex flex-col items-center justify-center">
        <AnimatePresence exitBeforeEnter>{children}</AnimatePresence>
      </main>
    </div>
  );
};

export default Layout;
import HeroSection from '../components/HeroSection';
import ServicesSection from '../components/ServicesSection';
import WhyChooseUs from '../components/WhyChooseUs';
import ReviewsSection from '../components/ReviewsSection';
import ContactSection from '../components/ContactSection';
import FloatingButton from '../components/FloatingButton';

const Home = () => {
  return (
    <>
      <HeroSection />
      <ServicesSection />
      <WhyChooseUs />
      <ReviewsSection />
      <ContactSection />
      <FloatingButton />
    </>
  );
};

export default Home;
import { useEffect } from 'react';
import '../styles/globals.css';

function MyApp({ Component, pageProps }) {
  useEffect(() => {
    // Optional: Add WhatsApp floating button
    const script = document.createElement('script');
    script.src = 'https://cdnjs.cloudflare.com/ajax/libs/whatsapp-chat-support/2.0.0/index.min.js';
    script.async = true;
    document.body.appendChild(script);

    return () => {
      document.body.removeChild(script);
    };
  }, []);

  return <Component {...pageProps} />;
}

export default MyApp;
// tailwind.config.js
module.exports = {
  content: [
    './pages/**/*.{js,jsx,ts,tsx}',
    './components/**/*.{js,jsx,ts,tsx}',
  ],
  theme: {
    extend: {},
  },
  plugins: [],
};
@tailwind base;
@tailwind components;
@tailwind utilities;

* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

html {
  font-family: 'Inter', sans-serif;
}

body {
  line-height: 1.6;
}

.animate-fade-in {
  animation: fadeIn 0.5s ease-in-out;
}

@keyframes fadeIn {
  from { opacity: 0; }
  to { opacity: 1; }
}
