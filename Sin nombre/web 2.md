# Master's Degree in Web Design & Full-Stack Development Roadmap

This curriculum roadmap is structured around a modern full-stack web development architecture based on the **LAMP stack**, **Laravel**, **Angular**, **TypeScript**, and modern front-end tooling.

## 🏗️ Technical Stack & Infrastructure Overview

The curriculum places a strong emphasis on server-side architecture and enterprise-grade front-end engineering.

### Server Architecture: LAMP + Laravel

- [**Linux**](https://www.kernel.org/ "null")**:** Core operating system for hosting, deployment, and permission management.
    
- [**Apache HTTP Server**](https://httpd.apache.org/ "null")**:** Web server handling HTTP routing, virtual hosts, and module integration.
    
- [**MySQL**](https://www.mysql.com/ "null")**:** Relational Database Management System (RDBMS) for structured data models.
    
- [**PHP**](https://www.php.net/ "null") & [Laravel](https://laravel.com/ "null"): Server-side logic, MVC architectural pattern, Eloquent ORM, and RESTful API development.
    

## 🛠️ Complete Tooling & Ecosystem Links

| **Icon** | **Tool / Technology** | **Category** | **Official Portal** |

| | **HTML5** | Front-end Markup | [W3C HTML5 Standard](https://html.spec.whatwg.org/ "null") |

| | **CSS3 & Styling** | Web Presentation | [W3C CSS Standards](https://www.w3.org/Style/CSS/ "null") |

| | **JavaScript (ES6+)** | Dynamic Scripting | [MDN JavaScript Documentation](https://developer.mozilla.org/en-US/docs/Web/JavaScript "null") |

| | **PHP** | Backend Language | [PHP Official Site](https://www.php.net/ "null") |

| | **Laravel** | PHP Framework | [Laravel Official Documentation](https://laravel.com/docs "null") |

| | **Angular** | Single Page Application Framework | [Angular Official Portal](https://angular.dev/ "null") |

| | **TypeScript** | Strongly Typed JS | [TypeScript Official Documentation](https://www.typescriptlang.org/ "null") |

| | **Sass / Preprocessors** | Advanced CSS Tooling | [Sass Official Documentation](https://sass-lang.com/ "null") |

| | **Webpack** | Module Bundler & Build Tools | [Webpack Official Site](https://webpack.js.org/ "null") |

| | **Node.js** | JS Runtime Environment | [Node.js Official Site](https://nodejs.org/ "null") |

| | **npm** | Package Manager | [npm Registry](https://www.npmjs.com/ "null") |

| | **VS Code** | Development Environment | [Visual Studio Code](https://code.visualstudio.com/ "null") |

| | **Open Source Initiative** | Licensing & Capstone Standards | [Open Source Initiative](https://opensource.org/ "null") |

## 📚 Curriculum Structure & Subject Breakdown

### Semester 1 (18 ECTS)

- [**HTML y CSS**](https://developer.mozilla.org/en-US/docs/Web/HTML "null") (6 ECTS) — Semantic structure, modern layouts (Flexbox & Grid), and responsive design.
    
- 🎨 [**Diseño de interfaces interactivas**](https://www.interaction-design.org/ "null") (6 ECTS) — Prototyping, usability, UI design patterns, and accessibility (WCAG).
    
- [**Programación en JavaScript para programadores**](https://developer.mozilla.org/en-US/docs/Web/JavaScript "null") (6 ECTS) — DOM manipulation, asynchronous execution, promises, and modern ECMAScript specifications.
    

_Note for non-CS background students: Complementary training in JavaScript (Introducción I & II - 8 ECTS total) is undertaken during this semester._

### Semester 2 (18 ECTS)

- [**Desarrollo back-end con PHP**](https://laravel.com/ "null") (6 ECTS) — PHP architecture, databases with MySQL, REST API design, and Laravel framework.
    
- [**Desarrollo front-end con frameworks JavaScript**](https://angular.dev/ "null") (6 ECTS) — Component architecture, data binding, routing, and state management using Angular.
    
- [**Herramientas HTML y CSS I**](https://sass-lang.com/ "null") (6 ECTS) — Preprocessors (Sass/SCSS), architecture patterns (BEM), and modular styling systems.
    

### Semester 3 (12 ECTS)

- [**Desarrollo front-end avanzado**](https://www.typescriptlang.org/ "null") (6 ECTS) — Advanced application architecture with TypeScript, strict type safety, and reactive programming.
    
- [**Herramientas HTML y CSS II**](https://webpack.js.org/ "null") (6 ECTS) — Modern build pipelines, Webpack bundling, Node/npm scripts, and performance optimization.
    

### Semester 4 (12 ECTS)

- [**Trabajo final de máster (TFM)**](https://opensource.org/ "null") (12 ECTS) — Full-stack capstone project integrating LAMP/Laravel backend, Angular/TypeScript frontend, and modern web design workflows.

---



the **LAMP technology** represents the core server environment (**L**inux, **A**pache, **M**ySQL, **P**HP).

For  educational purposes, i used  two primary ways to run a free server:  **locally** on a PC and hosted **in the cloud**.

### 1. Local Development Servers (Recommended for Students)

For the  web development courses i installed a local LAMP stack directly on my workstation. This runs Apache, MySQL, and PHP inside my  computer for instant testing.
 

- **XAMPP (or MAMP / WampServer)**:
         A completely free, cross-platform local server suite that bundles Apache, MariaDB/MySQL, and PHP into a single control panel.   It allows  to run a Laravel back-end and interface with MySQL without needing a remote server.
                         
- **WSL 2 (Windows Subsystem for Linux) + Native LAMP Stack**:
         Installing native Linux ( Ubuntu) inside Windows, then installing Apache, MySQL, and PHP directly via the Linux terminal (`sudo apt install apache2 mysql-server php`).  Linux administration and production environments, configuring a native Linux environment inside WSL mirror real-world production servers most accurately.        

### 2. Free Cloud & Server Options (For Live Deployment)

Forr PHP/Laravel back-end and MySQL database live on the internet, i used the following free cloud tiers for academic purpouses:

  - **Oracle Cloud Free Tier (Always Free Compute)**
  -       Oracle offers two free Linux Virtual Machines (VPS) with persistent storage permanently free. It allows to manually install Apache, MySQL, and PHP on an actual Linux cloud instance, giving you a full, production-grade cloud LAMP server for zero cost.      
                  
- **Render or Fly.io (Free / Hobby Tier)**
-      Cloud platforms that let you deploy Web Services (PHP/Laravel) and managed databases (MySQL/PostgreSQL) directly from GitHub repositories. Great for quick TFM (Trabajo Final de Máster) demonstrations without managing low-level Linux configuration.
        
                
- **Free Shared PHP Hosting (e.g., InfinityFree / 000webhost alternatives)**
     Traditional web hosts offering free Apache + MySQL + PHP hosting via a browser dashboard (cPanel).  Easiest to upload raw HTML/CSS/PHP files via FTP, though less flexible for modern frameworks like Laravel.