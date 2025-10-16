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

## 📝 License

MIT