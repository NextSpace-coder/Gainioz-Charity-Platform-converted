# Charity Platform

A comprehensive React-based charity and donation platform designed to empower communities through effective fundraising and volunteer management.

## Features

- **Multiple Home Layouts**: 4 different homepage designs
- **Donation Management**: Complete donation tracking and processing
- **E-commerce Integration**: Shop for charity merchandise
- **Event Management**: Organize and promote charity events
- **Volunteer System**: Recruit and manage volunteers
- **Blog Platform**: Share stories and updates
- **Modern Design**: Clean and inspiring UI/UX
- **React 18**: Built with the latest React features
- **Material-UI**: Professional design components
- **Supabase Integration**: Backend-as-a-Service for data management
- **Redux State Management**: Centralized application state
- **Advanced Animations**: GSAP and React Awesome Reveal
- **Mobile Responsive**: Optimized for all devices
- **SEO Optimized**: Meta tags and structured data

## Quick Start

1. **Clone the repository**
   ```bash
   git clone [repository-url]
   cd charity-platform
   ```

2. **Install dependencies**
   ```bash
   npm install
   ```

3. **Set up environment variables**
   ```bash
   cp .env.example .env
   ```
   Edit `.env` with your Supabase credentials:
   ```
   REACT_APP_SUPABASE_URL=https://your-project.supabase.co
   REACT_APP_SUPABASE_ANON_KEY=your-anon-key
   ```

4. **Start development server**
   ```bash
   npm start
   ```

5. **Build for production**
   ```bash
   npm run build
   ```

## Supabase Setup

1. Create a new project at [supabase.com](https://supabase.com)
2. Get your project URL and anonymous key from Settings > API
3. Update the environment variables in `.env`

### Database Schema Examples

```sql
-- Donations table
CREATE TABLE donations (
  id BIGSERIAL PRIMARY KEY,
  donor_name TEXT NOT NULL,
  donor_email TEXT NOT NULL,
  amount DECIMAL(10,2) NOT NULL,
  cause TEXT NOT NULL,
  message TEXT,
  is_anonymous BOOLEAN DEFAULT FALSE,
  created_at TIMESTAMP WITH TIME ZONE DEFAULT NOW()
);

-- Events table
CREATE TABLE events (
  id BIGSERIAL PRIMARY KEY,
  title TEXT NOT NULL,
  description TEXT,
  date_time TIMESTAMP WITH TIME ZONE,
  location TEXT,
  capacity INTEGER,
  registered_count INTEGER DEFAULT 0,
  created_at TIMESTAMP WITH TIME ZONE DEFAULT NOW()
);

-- Volunteers table
CREATE TABLE volunteers (
  id BIGSERIAL PRIMARY KEY,
  name TEXT NOT NULL,
  email TEXT NOT NULL,
  phone TEXT,
  skills TEXT[],
  availability TEXT,
  message TEXT,
  created_at TIMESTAMP WITH TIME ZONE DEFAULT NOW()
);

-- Stories table
CREATE TABLE stories (
  id BIGSERIAL PRIMARY KEY,
  title TEXT NOT NULL,
  content TEXT NOT NULL,
  author TEXT NOT NULL,
  featured_image TEXT,
  is_published BOOLEAN DEFAULT FALSE,
  created_at TIMESTAMP WITH TIME ZONE DEFAULT NOW()
);

-- Newsletter subscriptions table
CREATE TABLE newsletter (
  id BIGSERIAL PRIMARY KEY,
  email TEXT UNIQUE NOT NULL,
  subscribed_at TIMESTAMP WITH TIME ZONE DEFAULT NOW()
);
```

## Project Structure

```
src/
├── components/          # Reusable UI components
│   ├── BlogSection/    # Blog listing components
│   ├── ContactForm/    # Contact and inquiry forms
│   ├── DonationList/   # Donation campaign listings
│   ├── FeaturesSection/ # Feature highlights
│   ├── StoriesSection/ # Success stories
│   ├── TeamSection/    # Team member profiles
│   ├── header/         # Header and navigation
│   ├── footer/         # Footer components
│   └── hero/           # Hero section variants
├── main-component/     # Page components
│   ├── HomePage/       # Home page layouts
│   ├── AboutUsPage/    # About page
│   ├── DonationListing/ # Donation campaigns
│   ├── EventPage/      # Events listing
│   ├── BlogPage/       # Blog and news
│   ├── ContactPage/    # Contact information
│   └── ShopPage/       # E-commerce features
├── store/              # Redux store configuration
├── api/                # API functions and data
├── css/                # Stylesheets
└── lib/                # Utility functions and Supabase config
```

## Available Scripts

- `npm start` - Start development server
- `npm run build` - Build for production
- `npm test` - Run tests
- `npm run eject` - Eject from Create React App

## Home Page Layouts

1. **HomePage** - Classic charity layout with donation focus
2. **HomePage2** - Community-centered design
3. **HomePage3** - Impact-focused with statistics
4. **HomePage4** - Modern minimalist approach

## Pages Included

- **Multiple Home Layouts** - Various charity focuses
- **About Us** - Mission, vision, and team information
- **Donation Campaigns** - Active fundraising initiatives
- **Events** - Upcoming charity events and activities
- **Blog/Stories** - Success stories and news
- **Volunteer** - Volunteer opportunities and registration
- **Shop** - Charity merchandise and products
- **Contact** - Contact forms and information
- **Team** - Staff and volunteer profiles

## Key Components

### Donation System
- Campaign listings with progress tracking
- Donation forms with multiple payment options
- Donor recognition and testimonials
- Impact reporting and transparency

### Event Management
- Event listings with registration
- Calendar integration
- Capacity management
- Event details and gallery

### E-commerce Features
- Product catalog with categories
- Shopping cart functionality
- Checkout process
- Order management

### Content Management
- Blog system with categories
- Success story showcases
- Image galleries and lightbox
- Social sharing integration

## Customization

### Styling
- SCSS files in `src/css/`
- Material-UI theme customization
- Responsive design with Bootstrap 5
- Custom animations with GSAP

### Content
- Update API data in `src/api/` directory
- Modify component content in their respective files
- Replace images in `public/` and `src/images/` directories

### Branding
- Update logos in header and footer components
- Modify color scheme in theme configuration
- Update favicon and manifest in `public/` directory

## Dependencies

### Core
- React 18.0.0
- React Router DOM 6.3.0
- Material-UI 5.11.0

### Supabase & Data
- @supabase/supabase-js
- react-query
- Redux & Redux Toolkit
- Redux Persist

### UI Components & Animations
- Bootstrap 5.3.3
- GSAP 3.12.3
- React Awesome Reveal 4.2.5
- React Slick 0.29.0
- Swiper 9.3.0
- React CountUp 6.4.2

### Form & Interactions
- React DatePicker 6.9.0
- Simple React Validator 1.6.2
- React Toastify 9.1.2
- React Modal Video 2.0.1

### Advanced Features
- React Scroll Parallax 3.4.2
- React Medium Image Zoom 5.2.10
- React Responsive Masonry 2.1.7
- Yet Another React Lightbox 3.12.3

## Browser Support

- Chrome (latest)
- Firefox (latest)
- Safari (latest)
- Edge (latest)

## Security Considerations

- Environment variables for sensitive data
- Input validation on all forms
- Secure donation processing integration required
- User data protection compliance

## Performance Optimizations

- Code splitting with React.lazy
- Image optimization and lazy loading
- Bundle size optimization
- Efficient Redux state management

## License

This project is licensed under the MIT License.

## Support

For support and questions, please contact the development team or create an issue in the repository.
