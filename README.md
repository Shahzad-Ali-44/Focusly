#  Focusly - Stay Focused, Achieve More

A modern, beautiful productivity app designed to help you maintain focus and accomplish your goals. Built with React, TypeScript, and Supabase for real-time task management with secure user authentication.

![Focusly App](https://img.shields.io/badge/React-19.1.0-blue?style=for-the-badge&logo=react)
![TypeScript](https://img.shields.io/badge/TypeScript-5.8.3-blue?style=for-the-badge&logo=typescript)
![Vite](https://img.shields.io/badge/Vite-7.0.4-purple?style=for-the-badge&logo=vite)
![Tailwind CSS](https://img.shields.io/badge/Tailwind-4.1.11-38B2AC?style=for-the-badge&logo=tailwind-css)
![Supabase](https://img.shields.io/badge/Supabase-2.53.0-green?style=for-the-badge&logo=supabase)

##  Features

###  **Core Functionality**
- **User Authentication**: Secure signup and login with Supabase Auth
- **Task Management**: Create, edit, and delete tasks with ease
- **Progress Tracking**: Real-time progress visualization with beautiful charts
- **Task Completion**: Mark tasks as complete with smooth animations
- **Statistics Dashboard**: View total tasks, completed tasks, and progress percentage
- **User-Specific Data**: Each user can only access their own tasks

###  **User Experience**
- **Dark/Light Mode**: Seamless theme switching with system preference detection
- **Responsive Design**: Works perfectly on desktop, tablet, and mobile
- **Beautiful UI**: Modern gradient backgrounds and smooth animations
- **Real-time Sync**: Instant updates across all devices using Supabase
- **Toast Notifications**: Interactive notifications for all user actions
- **Auto-complete Forms**: Enhanced form experience with browser autofill

###  **Technical Features**
- **TypeScript**: Full type safety and better development experience
- **Real-time Database**: Supabase for instant data synchronization
- **Row Level Security**: Database-level security for user data isolation
- **Modern Stack**: React 19, Vite, Tailwind CSS 4
- **PWA Ready**: Progressive Web App capabilities
- **SEO Optimized**: Meta tags and structured data for better discoverability

## 🛠 Tech Stack

### **Frontend**
- **React 19** 
- **TypeScript** 
- **Vite** 
- **Tailwind CSS 4** 
- **Lucide React** 

### **Backend & Database**
- **Supabase** 
- **PostgreSQL** 

### **UI Components**
- **Radix UI** 
- **shadcn/ui** 
- **Class Variance Authority** 

### **Development Tools**
- **ESLint** 
- **TypeScript ESLint**

##  Getting Started

### Prerequisites
- Node.js 18+ 
- npm or yarn
- Supabase account

### Installation

1. **Clone the repository**
   ```bash
   git remote add origin https://github.com/Shahzad-Ali-44/Focusly.git

   cd Focusly
   ```

2. **Install dependencies**
   ```bash
   npm install
   ```

3. **Set up Supabase**
   - Create a new project at [supabase.com](https://supabase.com)
   - Enable Authentication in your Supabase dashboard
   - Create a table named `Focusly` with the following schema:
   ```sql
   CREATE TABLE Focusly (
     id UUID DEFAULT gen_random_uuid() PRIMARY KEY,
     title TEXT NOT NULL,
     is_complete BOOLEAN DEFAULT FALSE,
     created_at TIMESTAMP WITH TIME ZONE DEFAULT NOW(),
     user_id UUID REFERENCES auth.users(id)
   );
   
   ALTER TABLE Focusly ENABLE ROW LEVEL SECURITY;
   
   CREATE POLICY "Users can only see their own tasks" ON Focusly 
   FOR ALL USING (auth.uid() = user_id);
   ```

4. **Environment Variables**
   Create a `.env` file in the root directory:
   ```env
   VITE_SUPABASE_URL=your_supabase_project_url
   VITE_SUPABASE_ANON_KEY=your_supabase_anon_key
   ```

5. **Run the development server**
   ```bash
   npm run dev
   ```

6. **Open your browser**
   Navigate to `http://localhost:5173`

##  Usage

### **Authentication**
- **Sign Up**: Create a new account with your email and password
- **Sign In**: Login with your existing credentials
- **Logout**: Securely logout from your account
- **User Isolation**: Each user can only access their own tasks

### **Adding Tasks**
- Type your task in the input field
- Press Enter or click "Add Task"
- Tasks are automatically saved to your personal database

### **Managing Tasks**
- **Complete**: Click the circle button next to any task
- **Delete**: Click the trash icon to remove a task
- **Progress**: View your completion percentage in real-time
- **Scrollable List**: Scroll through tasks when you have many

### **Theme Switching**
- Click the theme toggle button in the top-right corner
- Choose between light, dark, or system preference


##  Key Features Explained

### **User Authentication**
Secure authentication system using Supabase Auth with:
- Email/password signup and login
- Session management
- Automatic logout on session expiry
- User-specific data isolation

### **Real-time Sync**
Tasks are instantly synchronized across all devices using Supabase's real-time subscriptions.

### **Progress Tracking**
The app calculates and displays:
- Total number of tasks
- Completed tasks count
- Progress percentage with visual progress bar

### **Row Level Security**
Database-level security ensures:
- Users can only access their own tasks
- Complete data isolation between users
- Secure API endpoints

### **Responsive Design**
Built with mobile-first approach using Tailwind CSS responsive utilities.

### **Accessibility**
All components are built with accessibility in mind using Radix UI primitives.

##  Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

##  License

This project is licensed under the MIT [LICENSE](LICENSE).

##  Author

**Shahzad Ali**
- Portfolio: [shahzadali.vercel.app](https://shahzadali.vercel.app)
- LinkedIn: [Shahzad Ali](https://www.linkedin.com/in/shahzad-ali-8817632ab)

