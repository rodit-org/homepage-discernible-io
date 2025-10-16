# homepage-discernible-io

A modern, responsive static homepage for Discernible.io built with HTML, CSS, and JavaScript.

## 🚀 Features

- **Modern Design**: Clean, gradient-based design with smooth animations
- **Fully Responsive**: Works seamlessly on desktop, tablet, and mobile devices
- **Interactive Elements**: Smooth scrolling, form handling, and scroll animations
- **Performance Optimized**: Lightweight static site with no build dependencies

## 📁 Project Structure

```
homepage-discernible-io/
├── public/
│   ├── index.html      # Main HTML file
│   ├── styles.css      # CSS styling
│   └── script.js       # JavaScript functionality
├── certs/              # SSL/TLS certificate management
│   ├── README.md       # Complete certificate setup guide
│   ├── setup-all.sh    # Automated setup script
│   └── ...             # Management scripts and configs
├── .do/
│   └── app.yaml        # Digital Ocean App Platform configuration
├── package.json        # Node.js package configuration
└── README.md          # This file
```

## 🌐 Deployment on Digital Ocean App Platform

### Method 1: Using the Web Interface

1. Go to [Digital Ocean App Platform](https://cloud.digitalocean.com/apps)
2. Click "Create App"
3. Select your GitHub repository
4. Digital Ocean will automatically detect the `package.json` and configure as a static site
5. Set the following in the configuration:
   - **Source Directory**: `/public`
   - **Output Directory**: `/public`
   - Click "Next" and deploy

### Method 2: Using the App Spec (app.yaml)

The `.do/app.yaml` file is already configured. Digital Ocean will automatically use this configuration when deploying.

## 🏃 Running Locally

To run this site locally:

```bash
# Install http-server globally (one-time setup)
npm install -g http-server

# Run the development server
npm start
```

Then open your browser to `http://localhost:8080`

Alternatively, you can use any static file server:

```bash
# Using Python 3
cd public
python3 -m http.server 8080

# Using PHP
cd public
php -S localhost:8080
```

## 🎨 Customization

- **Colors**: Edit CSS variables in `public/styles.css` under `:root`
- **Content**: Modify text and structure in `public/index.html`
- **Functionality**: Add or modify JavaScript in `public/script.js`

## 🔒 SSL/TLS Certificate Setup (Apache2)

For production deployment with SSL/TLS certificates using Apache2 and Let's Encrypt:

### Quick Setup
```bash
cd certs
./setup-all.sh
```

This will:
- ✅ Configure Apache2 web server
- ✅ Obtain free SSL certificates from Let's Encrypt
- ✅ Set up automatic certificate renewal
- ✅ Configure security headers (HSTS, CSP, etc.)
- ✅ Enable HTTPS with automatic HTTP redirect
- ✅ Set up monitoring and backups

### Documentation
- **[Complete Guide](certs/README.md)** - Detailed setup instructions
- **[Quick Start](certs/QUICKSTART.md)** - Quick reference commands
- **[DNS Setup](certs/DNS-SETUP.md)** - DNS configuration guide
- **[Checklist](certs/CHECKLIST.md)** - Step-by-step verification
- **[Summary](certs/SUMMARY.md)** - Package overview

### Prerequisites
- Ubuntu/Debian server with sudo access
- DNS records pointing to your server:
  - `discernible.io` → your_server_ip
  - `www.discernible.io` → your_server_ip
- Ports 80 and 443 open

### Features
- 🔐 Free SSL certificates from Let's Encrypt
- 🤖 Automated certificate renewal
- 📊 Certificate expiry monitoring
- 💾 Automated weekly backups
- 🔒 Security headers (A+ rating)
- 📧 Email notifications
- 🧪 Comprehensive testing tools

## 📝 License

MIT