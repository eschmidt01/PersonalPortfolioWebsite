# Personal Portfolio Website

<details>
  <summary>View Sample Screenshots</summary>

  ### Sample Screenshots
  Here are two screenshots showcasing the portfolio webpage:
  ![Screenshot 1](https://github.com/user-attachments/assets/3882232e-46f3-490f-a913-0c2ea5d1439b)
  ![Screenshot 2](https://github.com/user-attachments/assets/8b39e931-cebc-4590-96de-f52bd0d2a1cc)

</details>

## Overview

This mock web application is a personal portfolio designed to showcase skills, projects, and accomplishments. It features interactive elements like a project gallery, testimonials, a downloadable resume, and contact options for networking.

## Architecture

The proposed web application would use a Flask backend to serve dynamic content and handle form submissions. Here's how the architecture would be structured:

### Backend (Flask)

- **Routes and HTTP Methods:**
  - `GET /`: Serves the main portfolio page.
  - `GET /projects`: Retrieves project data to display in the gallery.
  - `GET /projects/<id>`: Retrieves details for a specific project.
  - `POST /contact`: Handles contact form submissions.
  - `GET /resume`: Serves the downloadable resume PDF.
  - `GET /testimonials`: Retrieves approved testimonials to display.
  - `POST /testimonials`: Allows submission of new testimonials (pending approval).
  - `GET /blog`: Retrieves blog posts.
  - `GET /blog/<id>`: Retrieves a specific blog post.
  - `POST /testimonial-submission`: Handles new testimonial submissions.

- **Database Schema:**

  - **Users Table:**
    - `id` (Primary Key)
    - `name`
    - `email`
    - `password` (hashed)

  - **Projects Table:**
    - `id` (Primary Key)
    - `title`
    - `description`
    - `thumbnail_url`
    - `details`
    - `skills` (Many-to-Many relationship with Skills Table)

  - **Skills Table:**
    - `id` (Primary Key)
    - `name`
    - `icon_url`

  - **Testimonials Table:**
    - `id` (Primary Key)
    - `author_name`
    - `author_role`
    - `content`
    - `approved` (Boolean)

  - **Messages Table (Contact Form Submissions):**
    - `id` (Primary Key)
    - `name`
    - `email`
    - `message`
    - `date_submitted`

  - **Blog Posts Table:**
    - `id` (Primary Key)
    - `title`
    - `content`
    - `excerpt`
    - `date_posted`
    - `category`

### Frontend Interaction

- **Project Gallery:**
  - Fetches project data from `/projects` endpoint.
  - Displays projects with thumbnails and modals for details.

- **Contact Form:**
  - Submits data to `/contact` via POST.
  - Uses AJAX for smooth user experience.

- **Testimonials:**
  - Displays approved testimonials from `/testimonials`.
  - New submissions sent to `/testimonial-submission` via POST for approval.

- **Resume Download:**
  - Link points to `/resume`, which triggers a file download.

- **Blog Section:**
  - Fetches blog posts from `/blog` endpoint.
  - Displays excerpts with links to full posts.

- **Skills Filter:**
  - Filters projects displayed in the gallery based on selected skills.

## Browsers for Testing

- Chrome
- Firefox
- Edge
- Safari

## Future Enhancements

- Implement user authentication for a secured admin panel.
- Add analytics to track user interactions.
- Optimize images and assets for faster load times.

