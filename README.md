# **RegeneraX - Regenerative City Operating System**

## **Overview**
RegeneraX is an AI-powered urban intelligence platform that transforms cities into living, adaptive ecosystems. By combining government sensor data, satellite information, and citizen-reported issues, it creates a comprehensive digital twin of urban infrastructure to guide regenerative city planning and responsive governance.

---

## **What It Does**
RegeneraX acts as a **"City Brain"** — a cognitive layer that perceives urban environments through multiple data streams and provides actionable insights for city planners, administrators, and citizens.

The platform:

- **Aggregates Multi-Source Data:** Integrates real-time government APIs (air quality, rainfall, power grids, groundwater levels, soil health) with citizen-generated reports from a partner mobile application  
- **AI-Powered Analysis:** Uses Google Gemini AI to process thousands of data points, identify patterns, prioritize critical issues, and generate intelligent urban insights  
- **Interactive Visualization:** Maps all data on an interactive geographical interface with color-coded markers indicating issue severity and environmental health metrics  
- **Intelligent Chatbot:** Provides conversational access to city data, allowing users to query about pollution levels, infrastructure issues, and environmental trends  

---

## **Core Features**

### **1. Multi-Layer Data Integration**

#### **Government APIs**  
Fetches live data from India's Open Government Data platform including:

- Air Quality Index (AQI)  
- Rainfall patterns  
- Power grid status  
- Groundwater levels  
- Soil health metrics  

#### **Citizen Reports (Firebase)**
- Infrastructure issues (potholes, broken roads)  
- Waste management problems  
- Public facility degradation  
- Environmental concerns  

---

### **2. LangGraph AI Workflow**

Three-node AI pipeline:

- **Data Aggregator** – Collects government and citizen data  
- **City Analyst** – AI categorizes issues, extracts sentiment, merges insights  
- **Cartographer** – Geocodes locations, assigns fallback coordinates, creates markers  

---

### **3. Interactive Map Dashboard**
- Real-time React Leaflet visualization  
- Color-coded markers (green = good, red = issues)  
- Popup details for each marker  
- Floating panels with AQI, rainfall, power data, report stats  

---

### **4. AI Assistant Chat**
- Gemini AI powered chatbot  
- Answers questions about pollution, issues, trends  
- Uses cached real-time city data  
- Simple natural language interface  

---

### **5. Citizen Engagement Portal**
- Partner mobile app  
- Upload geo-tagged photos  
- Auto GPS + category + timestamp  
- Real-time sync to Firebase  

---

## **Technology Stack**

### **Backend**
- FastAPI  
- LangChain + LangGraph  
- Google Gemini AI  
- Firebase Admin SDK  
- Geopy  
- Python-dotenv  

### **Frontend**
- React 19  
- Vite  
- Tailwind CSS v4  
- React Leaflet  
- Axios  
- Lucide React  
- Framer Motion  

### **Infrastructure**
- Firebase Firestore  
- Open Government Data API  
- Nominatim OSM  

---

## **How It Works**

### **Workflow Pipeline**

#### **1. User Input**
User enters a city name (e.g., "Bangalore", "Mumbai", "Delhi").

#### **2. Data Aggregation Phase**
- Backend fetches government data  
- Retrieves all citizen reports from Firebase  
- Geocodes city center  

#### **3. AI Analysis Phase**
- Gemini AI extracts location, category, sentiment  
- Merges citizen + government data  

#### **4. Cartography Phase**
- Geocodes all locations  
- Applies fallback (city center + random offset)  
- Generates map markers  

#### **5. Visualization**
- React Leaflet map loads markers  
- Side panels show AQI, rainfall, power, citizen stats  
- Chatbot loads with cached city data  

#### **6. Interactive Query**
- User asks a question  
- AI fetches cached city data  
- Responds with accurate insights  

---

## **Key Capabilities**

### **For City Planners**
- Identify pollution hotspots  
- Monitor infrastructure degradation  
- Prioritize interventions  
- Track water/energy/waste flows  

### **For Citizens**
- Report issues from mobile app  
- View city health metrics  
- Get environmental info via chat  
- Track issue resolution  

### **For Administrators**
- Full urban dashboard  
- Trend analysis  
- Evidence-based decisions  
- Respond to public reports  

---

## **Data Sources**

### **Government APIs (api.data.gov.in)**
- AQI  
- Rainfall  
- Power Grid  
- Groundwater  
- Soil Health  

### **Citizen Mobile App**
- Geo-tagged images  
- Auto GPS + timestamp  
- Category selection  
- Real-time Firebase sync  

---

## **Environmental Impact**
RegeneraX supports regenerative development through:

- Reduced response times  
- Data-driven decisions  
- Citizen empowerment  
- Smart resource allocation  
- Climate adaptation readiness  

---

## **Installation & Setup**

### **Prerequisites**
- Node.js 16+  
- Python 3.8+  
- Firebase account  
- Google Gemini API key  
- Government Data API key  

---

## **Backend Setup**
```bash
cd backend
pip install -r requirements.txt

# .env file
# GOOGLE_API_KEY=your_gemini_api_key
# GOVT_DATA_API=your_ogd_api_key

# Add Firebase service account key as serviceAccountKey.json

python main.py
# Runs on http://localhost:8000
```

---

## **Frontend Setup**
```bash
cd frontend
npm install
npm run dev
# Runs on http://localhost:5173
```

---

## **API Endpoints**

### **POST /analyze-city**
Returns:
```json
{
  "city": "Bangalore",
  "city_center": [12.9716, 77.5946],
  "map_markers": [...],
  "gov_data": {...},
  "citizen_stats": {...}
}
```

### **POST /chat**
```json
{
  "city": "Mumbai",
  "message": "What is the air quality today?"
}
```

---

## **Future Enhancements**
- Predictive analytics  
- Historical trends  
- Multi-city comparison  
- Mobile app dashboard  
- Alerts & notifications  
- Satellite imagery integration  
- Carbon footprint tracking  

---

## **Contributing**
Contributions welcome for:
- More data integrations  
- AI improvements  
- UI/UX enhancements  
- Mobile app  
- Testing & documentation  

---

## **License**
Built for hackathons and educational use to demonstrate AI-driven civic technology.

---

## **Acknowledgments**
- Open Government Data Platform India  
- Google Gemini AI  
- Firebase  
- OpenStreetMap  
- React & FastAPI communities  

---

**Built with ❤️ for smarter, regenerative cities.**
