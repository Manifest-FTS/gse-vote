# Garden State Equality PAC - Landing Page

A modern, mobile-responsive static landing page for Garden State Equality PAC focused on protecting equality in New Jersey.

## Features

- **Professional Design**: Clean, modern UI with a sticky navigation header
- **Responsive Layout**: Fully optimized for desktop, tablet, and mobile devices
- **Mission-Driven Content**: Clear messaging aligned with PAC objectives
- **Validated Signup Form**: Real-time validation with helpful error messages
- **Modern Styling**: Built with Tailwind CSS for a professional appearance
- **GitHub Pages Ready**: Static HTML optimized for free hosting

## Form Validation

The signup form includes comprehensive validation for:
- **First Name** (minimum 2 characters, required)
- **Last Name** (minimum 2 characters, required)
- **Email Address** (proper email format, required)
- **Zip Code** (5-digit or 5+4 digit US zip code format, required)

## Local Development

To view the page locally, you can use any local web server. Here are a few options:

### Using Python:
```bash
# Python 3
python -m http.server 8000

# Python 2
python -m SimpleHTTPServer 8000
```

Then open `http://localhost:8000` in your browser.

### Using Node.js:
```bash
npx serve
```

### Using VS Code:
Install the "Live Server" extension and right-click on `index.html` to select "Open with Live Server".

## GitHub Pages Deployment

### Initial Setup

1. **Create GitHub Repository**
   - Create a new repository (e.g., `gse-vote`)
   - Make sure the repository is public for free GitHub Pages hosting

2. **Push Your Code**
   ```bash
   git init
   git add .
   git commit -m "Initial commit: PAC landing page"
   git branch -M main
   git remote add origin https://github.com/YOUR-USERNAME/gse-vote.git
   git push -u origin main
   ```

3. **Enable GitHub Pages**
   - Go to your repository on GitHub
   - Navigate to **Settings** > **Pages**
   - Under **Source**, select `main` branch and `/ (root)` folder
   - Click **Save**

4. **Wait for Deployment**
   - GitHub Pages will build and deploy your site automatically
   - The site will be available at `https://YOUR-USERNAME.github.io/gse-vote/`

### Custom Domain Setup

The CNAME file is already configured for `gsq.vote`. To set up custom domains:

#### DNS Configuration

Add the following DNS records for each domain:

**For gsq.vote, gardenstateequality.vote, and gsequality.vote:**

1. **A Records** (for apex domain):
   ```
   185.199.108.153
   185.199.109.153
   185.199.110.153
   185.199.111.153
   ```

2. **CNAME Record** (for www subdomain):
   ```
   Type: CNAME
   Host: www
   Value: YOUR-USERNAME.github.io
   ```

#### GitHub Settings

1. Go to **Settings** > **Pages** in your GitHub repository
2. Under **Custom domain**, enter your primary domain (e.g., `gsq.vote`)
3. Check **Enforce HTTPS** (recommended, may take a few minutes to be available)

#### Multiple Domains

To point multiple domains (gsq.vote, gardenstateequality.vote, gsequality.vote) to the same GitHub Pages site:

1. The CNAME file should contain your primary domain (currently `gsq.vote`)
2. Configure DNS for all domains to point to your GitHub Pages:
   - Use A records for apex domains
   - Use CNAME records for www subdomains
3. Set up domain forwarding at your DNS provider to redirect secondary domains to your primary domain

## Form Integration

The form currently logs data to the console. To connect to a mailing list service:

### Option 1: Formspree
1. Sign up at [Formspree.io](https://formspree.io)
2. Create a new form and get your form endpoint
3. Update the `<form>` tag:
   ```html
   <form action="https://formspree.io/f/YOUR_FORM_ID" method="POST">
   ```

### Option 2: Netlify Forms
1. Host on Netlify instead of GitHub Pages
2. Add `netlify` attribute to form:
   ```html
   <form netlify name="signup">
   ```

### Option 3: Custom Backend
1. Set up your own backend endpoint
2. Modify the form submission JavaScript to POST to your endpoint

## Contact Information

For questions or support, contact: [fuscarino@gmail.com](mailto:fuscarino@gmail.com)

## Structure

```
gse-vote/
├── index.html          # Main landing page
├── CNAME              # Custom domain configuration for GitHub Pages
└── README.md          # This file
```

## Browser Support

- Chrome (latest)
- Firefox (latest)
- Safari (latest)
- Edge (latest)
- Mobile browsers (iOS Safari, Chrome Mobile)

## License

© 2025 Garden State Equality PAC. All rights reserved.
