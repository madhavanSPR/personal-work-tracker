# 📋 Personal Work Tracker

A modern, full-stack personal work management application built with Angular and PocketBase.

## 🌟 Features

- **📅 Task Management**: Create and track personal work tasks
- **🔗 Git Integration**: Link tasks with Git repositories
- **📊 Dynamic Forms**: Customizable field schemas
- **📈 Dashboard**: Visual overview of work progress
- **🏷️ Sub Modules**: Organize work into sub-components
- **👥 Team Management**: Assign tasks and track ownership
- **📱 Responsive Design**: Works on desktop and mobile
- **🎨 Material Design**: Clean, professional UI with Angular Material

## 🚀 Live Demo

- **Frontend**: [Deploy to Vercel](https://vercel.com/new/clone?repository-url=https://github.com/yourusername/personal-work-tracker)
- **Backend**: [Deploy to Railway](https://railway.app)

## 🏗️ Project Structure

```
personal-work-tracker/
├── frontend/          # Angular application
│   ├── src/
│   ├── package.json
│   ├── vercel.json    # Vercel deployment config
│   └── DEPLOYMENT.md  # Detailed deployment guide
├── backend/           # PocketBase backend
│   ├── pocketbase     # PocketBase binary
│   ├── pb_data/       # Database and configuration
│   ├── Dockerfile     # Docker configuration
│   └── railway.toml   # Railway deployment config
└── README.md
```

## ⚡ Quick Start

### Prerequisites
- Node.js 18+ and npm
- Git

### 1. Clone Repository
```bash
git clone https://github.com/yourusername/personal-work-tracker.git
cd personal-work-tracker
```

### 2. Start Backend (PocketBase)
```bash
cd backend
./pocketbase serve --http=0.0.0.0:8090
```

### 3. Start Frontend (Angular)
```bash
cd frontend
npm install
npm start
```

### 4. Access Application
- **Frontend**: http://localhost:4200
- **Backend Admin**: http://localhost:8090/_/

## 🛠️ Development Setup

### Backend Setup
1. Start PocketBase server
2. Create admin account at http://localhost:8090/_/
3. Import field schema from `frontend/clean-field-schema.json`

### Frontend Setup
1. Install dependencies: `npm install`
2. Start development server: `ng serve`
3. Build for production: `ng build --configuration=production`

## 🌐 Deployment

### Frontend (Vercel)
[![Deploy with Vercel](https://vercel.com/button)](https://vercel.com/new/clone?repository-url=https://github.com/yourusername/personal-work-tracker)

1. Connect GitHub repository to Vercel
2. Set build command: `ng build --configuration=production`
3. Set output directory: `dist/personal-work-tracker`

### Backend (Railway)
[![Deploy on Railway](https://railway.app/button.svg)](https://railway.app/new/template)

1. Connect GitHub repository to Railway
2. Railway will auto-detect Dockerfile
3. Update frontend environment with Railway URL

**📖 See [DEPLOYMENT.md](frontend/DEPLOYMENT.md) for detailed instructions**

## 🎯 Key Features

### Dynamic Form Builder
- Customizable field schemas
- Multiple input types (text, date, select, textarea)
- Dynamic sub-module management
- Form validation and error handling

### Task Management
- Create, read, update, delete tasks
- Filter and search functionality
- Drag-and-drop reordering
- Export/import capabilities

### Dashboard Analytics
- Task completion statistics
- Progress tracking
- Visual charts and graphs
- Monthly/yearly views

## 🔧 Technology Stack

### Frontend
- **Framework**: Angular 18
- **UI Library**: Angular Material
- **Styling**: SCSS with Material Design
- **Forms**: Reactive Forms
- **HTTP Client**: Angular HttpClient
- **Deployment**: Vercel

### Backend
- **Database**: PocketBase (SQLite)
- **API**: RESTful with real-time subscriptions
- **File Storage**: Built-in file handling
- **Admin UI**: Included web interface
- **Deployment**: Railway/Docker

## 📊 Database Schema

### Collections

#### field_schema
```json
{
  "key": "string",
  "label": "string",
  "data_type": "string",
  "required": "boolean",
  "display_in_form": "boolean", 
  "display_in_table": "boolean",
  "order": "number",
  "options": "array"
}
```

#### tasks
```json
{
  "date": "date",
  "git_id": "string",
  "git_link": "url", 
  "module": "string",
  "sub_modules": "json",
  "start_date": "date",
  "end_date": "date", 
  "task_assigned_by": "string",
  "requirement_owner": "string",
  "status": "string",
  "remarks": "text"
}
```

## 🤝 Contributing

1. Fork the repository
2. Create feature branch: `git checkout -b feature/amazing-feature`
3. Commit changes: `git commit -m 'Add amazing feature'`
4. Push to branch: `git push origin feature/amazing-feature`
5. Open Pull Request

## 📝 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🆘 Support

- 📖 [Documentation](frontend/DEPLOYMENT.md)
- 🐛 [Issue Tracker](https://github.com/yourusername/personal-work-tracker/issues)
- 💬 [Discussions](https://github.com/yourusername/personal-work-tracker/discussions)

## 🙏 Acknowledgments

- [Angular](https://angular.io/) - Frontend framework
- [Angular Material](https://material.angular.io/) - UI components
- [PocketBase](https://pocketbase.io/) - Backend solution
- [Vercel](https://vercel.com/) - Frontend hosting
- [Railway](https://railway.app/) - Backend hosting

---

**Built with ❤️ for personal productivity**
