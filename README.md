# SpaceAura

A cinematic, space-inspired landing page built with **Vue.js, GSAP, and Tailwind CSS**, focused on immersive visual design, smooth motion, and scroll-based interactions.

SpaceAura is a creative frontend project built to explore modern web animation techniques and create a dynamic browsing experience.

## Live Demo

[View SpaceAura](https://landing-page-amber-chi.vercel.app/)

## Features

* Cinematic hero section
* GSAP-powered animations
* Scroll-based interactions with ScrollTrigger
* Image reveal animations
* Text and element transitions
* Staggered animations
* Responsive design
* Mobile-specific animation handling
* Reusable Vue components
* Tailwind CSS styling

## Tech Stack

| Technology         | Usage                          |
| ------------------ | ------------------------------ |
| Vue.js 3           | Frontend framework             |
| JavaScript         | Application logic              |
| GSAP               | Animations and motion          |
| GSAP ScrollTrigger | Scroll-based animations        |
| Tailwind CSS       | Styling and responsive layouts |
| Vite               | Development and build tooling  |

## Animation

Animation is the core focus of SpaceAura.

The project explores different GSAP techniques to create a cinematic scrolling experience, including:

* GSAP timelines
* ScrollTrigger
* Scrub-based animations
* Image scaling and positioning
* Image reveal effects
* Staggered animations
* Text transitions
* Scroll-driven movement
* Responsive animation logic with `gsap.matchMedia()`

The goal was to make the page feel like one continuous visual experience rather than a collection of static sections.

## Project Structure

```text
Spaceaura/
│
├── Components/
│   └── ...
│
├── public/
│   └── ...
│
├── src/
│   └── ...
│
├── index.html
├── tailwind.config.js
├── vite.config.js
├── package.json
└── README.md
```

## Getting Started

### Prerequisites

Make sure you have Node.js and npm installed.

### Installation

Clone the repository:

```bash
git clone https://github.com/spystar20/Spaceaura.git
```

Navigate to the project:

```bash
cd Spaceaura
```

Install dependencies:

```bash
npm install
```

Start the development server:

```bash
npm run dev
```

Vite will provide a local development URL in the terminal.

## Build for Production

Create a production build:

```bash
npm run build
```

Preview the production build locally:

```bash
npm run preview
```

## Project Goals

SpaceAura was created to strengthen frontend development and animation skills while experimenting with creative web experiences.

The main goals were to:

* Practice building interfaces with Vue 3
* Develop stronger GSAP skills
* Understand ScrollTrigger in a real project
* Create responsive animation systems
* Experiment with image and text transitions
* Build reusable components
* Improve visual hierarchy and motion design

## What I Learned

While building SpaceAura, I worked with:

* Vue 3 Composition API
* Vue component architecture
* GSAP timelines
* ScrollTrigger configuration
* Scroll-linked animations
* Responsive GSAP animations
* `gsap.matchMedia()`
* Image clipping and reveal techniques
* Animation sequencing and staggering
* Integrating animation logic into reusable components

## Responsive Design

SpaceAura is designed to adapt across different screen sizes.

Desktop and mobile layouts use different animation approaches where necessary to keep interactions practical and visually consistent across devices.
