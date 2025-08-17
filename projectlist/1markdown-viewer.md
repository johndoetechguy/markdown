# Product Requirements Document (PRD): Real-Time Markdown Viewer

RealTimeMarkdownViewer

## 1. Executive Summary

### 1.1 Product Overview
The Real-Time Markdown Viewer is a web-based application that provides an intuitive interface for viewing, managing, and organizing markdown files with real-time auto-detection capabilities.  
The application automatically detects new markdown files as they are added to the file system and updates the user interface instantly without requiring page refreshes.

### 1.2 Vision Statement
To create a seamless, real-time markdown viewing experience that enables users to efficiently browse, view, and manage markdown documentation with automatic file system synchronization.

### 1.3 Success Metrics
- **Response Time**: File detection within 100ms of file system changes  
- **User Experience**: Zero manual refresh required for new content  
- **Reliability**: 99.9% uptime for real-time updates  
- **Performance**: Support for 1000+ markdown files with maintained responsiveness  

## 2. Product Goals & Objectives

### 2.1 Primary Goals
- **Real-Time File Detection**: Automatically detect and display new markdown files  
- **Intuitive Navigation**: Provide a clean, organized file tree interface  
- **Seamless Viewing**: Offer both preview and source code viewing modes  
- **External Storage**: Support configurable external file storage locations  
- **Docker Deployment**: Enable containerized deployment for consistency  

### 2.2 Key Success Factors
- **User Adoption**: Reduce time spent on manual file management by 80%  
- **Developer Experience**: Enable instant documentation updates without workflow interruption  
- **System Integration**: Seamlessly integrate with existing development workflows  

## 3. Target Audience

### 3.1 Primary Users

#### Software Developers
- Need quick access to project documentation  
- Require real-time updates for collaborative documentation  
- Value integrated development workflows  

#### Technical Writers
- Manage multiple markdown files simultaneously  
- Need instant preview capabilities  
- Require organized file structure navigation  

#### Project Managers
- Access project documentation quickly  
- Monitor documentation changes in real-time  
- Need clean, professional viewing interface  

### 3.2 User Personas

#### Persona 1: "Alex the Developer"
- **Role**: Senior Software Engineer  
- **Pain Points**: Manual refresh needed for documentation updates  
- **Scenarios**: Seamless documentation access during development  
- **Usage**: Daily, integrated with development workflow  



## 4. Core Features

### 4.1.1 File System Management

#### 1. Real-Time File Detection
- Automatically detect new markdown files (`.md`, `.markdown`)  
- Support directory structure monitoring  
- Instant UI updates without page refresh  
- WebSocket-based communication for real-time updates  

#### 2. External Directory Configuration
- Configurable markdown root directory  
- Support for absolute file paths  
- Persistent storage outside application container  
- Environment-based configuration management  

#### 3. File Operations
- View markdown files in preview mode  
- View markdown source code  
- Upload new markdown files via web interface  
- Maintain file hierarchy and organization  

### 4.1.2 User Interface Features

#### 1. File Tree Navigation
- Hierarchical directory structure display  
- Collapsible directories (collapsed by default)  
- Persistent expansion state during session  
- Visual indicators for file types and folder states  

#### 2. Viewing Modes
- **Preview Mode**: Rendered markdown with styling  
- **Source Mode**: Raw markdown code view  
- Toggle between modes with keyboard shortcuts  
- Responsive design for different screen sizes  

#### 3. Search Functionality
- Search by filename  
- Search within file content  
- Real-time search results filtering  
- Keyboard shortcut support (`Ctrl+F`)  

#### 4. Upload Functionality
- Drag-and-drop file upload  
- Browse and select file upload  
- Automatic file validation (`.md` files only)  
- Real-time file tree updates after upload  

### 4.1.3 Real-Time Features

#### 1. Live Updates
- WebSocket connection for real-time communication  
- Connection status indicator in header  
- Automatic reconnection on connection loss  
- File change notifications  

#### 2. File System Events
- New file detection and display  
- File deletion handling  
- File modification updates  
- Directory creation/deletion monitoring  



### 6.2.1 Frontend Components

1. **React Application**
   - Single Page Application (SPA)  
   - Component-based architecture  
   - Real-time state management  
   - WebSocket integration  

2. **Core Components**
   - `App`: Main application container  
   - `Header`: Navigation and controls  
   - `Sidebar`: File tree and search  
   - `MarkdownViewer`: Content display  
   - `FileTree`: Directory navigation  

3. **Services**
   - `fileService`: API communication  
   - `websocketService`: Real-time updates  
   - `markdownParser`: Content processing  

### 6.2.2 Backend Components

1. **Node.js Server**
   - Express.js framework  
   - RESTful API endpoints  
   - WebSocket server integration  
   - File system operations  

2. **Core Modules**
   - File system watcher (Chokidar)  
   - WebSocket server (WS)  
   - File upload handling (Multer)  
   - Configuration management  

### 6.3 Data Flow

1. **File Detection Flow**  
   File System Change → Chokidar Watcher → WebSocket Broadcast → Frontend Update  

2. **User Interaction Flow**  
   User Action → Frontend State → API Request → Backend Processing → WebSocket Update  

---

## 7. Technical Specifications

### 7.1 Technology Stack

#### 7.1.1 Frontend Technologies
- **Framework**: React 19.1.1  
- **Build Tool**: Vite 7.1.2  
- **Styling**: TailwindCSS 4.1.11  
- **Icons**: Lucide React 0.539.0  
- **HTTP Clients**: Fetch API  
- **WebSocket**: Native WebSocket API  

#### 7.1.2 Backend Technologies
- **Runtime**: Node.js 18 (Alpine Linux)  
- **Framework**: Express.js 4.18.2  
- **File Watching**: Chokidar 3.5.3  
- **WebSockets**: WS 8.14.2  
- **File Upload**: Multer 1.4.5  
- **CORS**: cors 2.8.5  


### 6.2.1 Frontend Components

1. **React Application**
   - Single Page Application (SPA)  
   - Component-based architecture  
   - Real-time state management  
   - WebSocket integration  

2. **Core Components**
   - `App`: Main application container  
   - `Header`: Navigation and controls  
   - `Sidebar`: File tree and search  
   - `MarkdownViewer`: Content display  
   - `FileTree`: Directory navigation  

3. **Services**
   - `fileService`: API communication  
   - `websocketService`: Real-time updates  
   - `markdownParser`: Content processing  

### 6.2.2 Backend Components

1. **Node.js Server**
   - Express.js framework  
   - RESTful API endpoints  
   - WebSocket server integration  
   - File system operations  

2. **Core Modules**
   - File system watcher (Chokidar)  
   - WebSocket server (WS)  
   - File upload handling (Multer)  
   - Configuration management  

### 6.3 Data Flow

1. **File Detection Flow**  
   File System Change → Chokidar Watcher → WebSocket Broadcast → Frontend Update  

2. **User Interaction Flow**  
   User Action → Frontend State → API Request → Backend Processing → WebSocket Update  

---

## 7. Technical Specifications

### 7.1 Technology Stack

#### 7.1.1 Frontend Technologies
- **Framework**: React 19.1.1  
- **Build Tool**: Vite 7.1.2  
- **Styling**: TailwindCSS 4.1.11  
- **Icons**: Lucide React 0.539.0  
- **HTTP Clients**: Fetch API  
- **WebSocket**: Native WebSocket API  

#### 7.1.2 Backend Technologies
- **Runtime**: Node.js 18 (Alpine Linux)  
- **Framework**: Express.js 4.18.2  
- **File Watching**: Chokidar 3.5.3  
- **WebSockets**: WS 8.14.2  
- **File Upload**: Multer 1.4.5  
- **CORS**: cors 2.8.5  


```
// Client receives

{
  "type": "file_added",
  "path": "docs/new-file.md",
  "structure": { /* updated file tree */ }
}

{
  "type": "file_deleted",
  "path": "docs/old-file.md",
  "structure": { /* updated file tree */ }
}

{
  "type": "directory_added",
  "path": "new-directory/",
  "structure": { /* updated file tree */ }
}

```

### 7.3 Configuration Management
```
// Environment Variables
PORT=3001
NODE_ENV=production
EXTERNAL_MARKDOWN_PATH=/path/to/markdown/files
CORS_ORIGIN=*
MAX_FILE_SIZE=10MB
ALLOWED_FILE_TYPES=.md,.markdown
```

## 8. User Experience Design
### 8.1 Interface Layout
- Headers: [Logo] [File Path] [Upload] [Preview/Source] [Live/Off]

```
Sidebar                  Main Content Area
-------------------------------------------------
Search Bar               Markdown Content
                         (Preview or Source)

File Tree
 ├── docs/
 │    ├── guides/
 │    ├── readme.md
 │    └── guide.md
```



