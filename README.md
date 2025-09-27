# SpeedAnalyzer - Web Performance Insights Tool

A comprehensive web performance analysis tool built with vanilla HTML, CSS, JavaScript, and PHP that provides detailed insights similar to Google PageSpeed Insights.

## Features

- **Performance Analysis**: Complete website performance scoring and metrics
- **Core Web Vitals**: FCP, LCP, CLS, TBT, and Speed Index measurements
- **Screenshot Capture**: Visual representation of analyzed websites
- **Detailed Audits**: Optimization opportunities and diagnostic information
- **Interactive UI**: Modern, responsive design with detailed explanations
- **Export Functionality**: Download analysis results as JSON
- **Comparison Tool**: Compare current analysis with previous results
- **Real User Data**: Chrome User Experience Report integration

## Requirements

- PHP 7.4 or higher
- Web server (Apache, Nginx, etc.)
- Google PageSpeed Insights API key
- cURL extension enabled
- JSON extension enabled
- Outbound HTTPS requests allowed

## Installation

1. **Get Google PageSpeed Insights API Key**
   - Go to [Google Cloud Console](https://console.developers.google.com/)
   - Create a new project or select existing one
   - Enable the PageSpeed Insights API
   - Create credentials (API Key)
   - Copy your API key

2. **Configure the Application**
   - Open `analyze.php`
   - Replace `YOUR_GOOGLE_PAGESPEED_API_KEY` with your actual API key
   - Save the file

3. **Upload Files**
   - Upload all files to your web server
   - Ensure PHP is enabled
   - Make sure server can make outbound HTTP requests

4. **Test the Application**
   - Open `index.html` in your browser
   - Enter a website URL to test
   - Click "Analyze" and wait for results

## File Structure

\`\`\`
speedanalyzer/
├── index.html          # Main application interface
├── analyze.php         # Backend API handler
├── config.php          # Configuration file
├── script.js           # Frontend JavaScript
├── styles.css          # Additional CSS styles
├── setup.html          # Setup instructions
└── README.md           # This file
\`\`\`

## API Configuration

Edit the `analyze.php` file and update the API key:

\`\`\`php
const API_KEY = 'YOUR_ACTUAL_API_KEY_HERE';
\`\`\`

## Features Overview

### Performance Metrics
- **Performance Score**: Overall performance rating (0-100)
- **Accessibility Score**: Accessibility compliance rating
- **Best Practices Score**: Web development best practices rating
- **SEO Score**: Search engine optimization rating

### Core Web Vitals
- **First Contentful Paint (FCP)**: Time until first content appears
- **Largest Contentful Paint (LCP)**: Time until main content loads
- **Total Blocking Time (TBT)**: Time page is blocked from user input
- **Cumulative Layout Shift (CLS)**: Visual stability measurement
- **Speed Index**: How quickly content is visually displayed

### Screenshot Functionality
- Automatic screenshot capture from PageSpeed Insights
- Fallback screenshot generation for blocked sites
- Full-size modal view with download capability
- Screenshot metadata display (dimensions, timestamp, type)

### Audit Results
- **Opportunities**: Performance improvement suggestions with potential savings
- **Diagnostics**: Technical issues and recommendations
- **Detailed Explanations**: Step-by-step fix instructions
- **Priority Levels**: High, medium, and low priority classifications

### Additional Features
- **Export Results**: Download analysis data as JSON
- **Comparison Tool**: Compare with previous analysis
- **Real User Data**: Chrome UX Report integration
- **Performance Timeline**: Visual timeline of loading events
- **Responsive Design**: Works on desktop and mobile devices

## Troubleshooting

### Common Issues

**Error: "Failed to connect to PageSpeed Insights API"**
- Check that your server can make outbound HTTPS requests
- Verify your API key is correct and active
- Ensure the PageSpeed Insights API is enabled in Google Cloud

**Error: "Invalid URL format"**
- Make sure the URL includes http:// or https://
- Verify the URL is properly formatted and accessible

**Error: "API Error: API key not valid"**
- Double-check your API key in `analyze.php`
- Verify the PageSpeed Insights API is enabled
- Check API key restrictions in Google Cloud Console

**Screenshot not available**
- Some websites block screenshot capture
- The tool will attempt fallback screenshot services
- Screenshots may not be available for all sites

### Server Requirements Check

Verify your server meets the requirements:

\`\`\`php
<?php
// Check PHP version
echo "PHP Version: " . phpversion() . "\n";

// Check required extensions
$required = ['curl', 'json'];
foreach ($required as $ext) {
    echo $ext . ": " . (extension_loaded($ext) ? "✓" : "✗") . "\n";
}

// Test outbound requests
$test = file_get_contents('https://www.google.com');
echo "Outbound HTTPS: " . ($test !== false ? "✓" : "✗") . "\n";
?>
\`\`\`

## Customization

### Styling
- Edit `styles.css` for custom styling
- Modify color scheme in CSS variables
- Adjust responsive breakpoints as needed

### API Configuration
- Update `config.php` for advanced settings
- Enable caching for better performance
- Configure rate limiting if needed

### Features
- Add custom audit rules in `analyze.php`
- Extend screenshot functionality
- Implement additional export formats

## Security Considerations

- Keep your API key secure and private
- Implement rate limiting for production use
- Validate and sanitize all user inputs
- Use HTTPS in production environments
- Consider implementing user authentication

## License

This project is open source and available under the MIT License.

## Support

For issues and questions:
1. Check the troubleshooting section
2. Review server requirements
3. Verify API key configuration
4. Test with different websites

## Contributing

Contributions are welcome! Please:
1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Test thoroughly
5. Submit a pull request

---

Built with ❤️ using vanilla web technologies and Google PageSpeed Insights API.
