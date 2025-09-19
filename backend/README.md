# Personal Work Tracker - Backend

This directory contains the PocketBase backend for the Personal Work Tracker application.

## 🚀 Quick Start

### Local Development
```bash
# Start PocketBase server
./pocketbase serve --http=0.0.0.0:8090

# Access admin panel
open http://localhost:8090/_/
```

### Initial Setup

1. **Start PocketBase** (if not already running)
2. **Create Admin Account**: Visit http://localhost:8090/_/
3. **Create Collections**:
   - `field_schema` - For form field definitions
   - `tasks` - For storing work tasks

4. **Import Data**: Use the JSON files from the frontend `/clean-field-schema.json`

## 🌐 Deployment Options

### Option 1: Railway (Recommended)
1. Connect this repo to Railway
2. Railway will automatically detect the Dockerfile
3. Your PocketBase will be deployed with a public URL

### Option 2: Docker
```bash
# Build image
docker build -t personal-work-tracker-backend .

# Run container
docker run -p 8090:8090 -v $(pwd)/pb_data:/app/pb_data personal-work-tracker-backend
```

### Option 3: PocketHost
1. Upload `pb_data` folder to [pockethost.io](https://pockethost.io)
2. Get your hosted PocketBase URL

## 📊 Collections Schema

### field_schema
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

### tasks
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
  "remarks": "text",
  "order_index": "number",
  "data": "json"
}
```

## 🔧 Configuration

### API Rules (Development)
For development, set all collection rules to allow public access:
- List/View Rule: `@request.auth.id != ""`
- Create Rule: `@request.auth.id != ""`  
- Update Rule: `@request.auth.id != ""`
- Delete Rule: `@request.auth.id != ""`

### CORS Settings
Add your frontend domains to CORS settings:
- `http://localhost:4200` (development)
- `https://your-app.vercel.app` (production)

## 🛠 Maintenance

### Backup Data
```bash
# Backup pb_data directory
tar -czf pb_data_backup_$(date +%Y%m%d).tar.gz pb_data/
```

### Update PocketBase
1. Download latest PocketBase binary
2. Replace the `pocketbase` file
3. Restart the service

## 📝 Environment Variables

For production deployment, you can configure:
- `PB_DATA_DIR`: Data directory path (default: `/app/pb_data`)
- `PB_PUBLIC_DIR`: Public files directory
- `PB_HOOKS_DIR`: Hooks directory

## 🔐 Security Notes

- Change default admin credentials after first setup
- Configure proper API rules for production
- Use HTTPS in production
- Regular backup of `pb_data` directory
- Monitor access logs

---

**PocketBase Version**: 0.22.20  
**Documentation**: [pocketbase.io/docs](https://pocketbase.io/docs)
