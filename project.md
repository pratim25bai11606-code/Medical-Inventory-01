PROJECT REPORTProject
 Name: MEDICARE — Medical Shop Inventory Management System
Technology Stack: Java (Swing/AWT), Pure File-Based I/O (CSV/Text), Custom Graphics2D 
  Target Environment: Cross-Platform Desktop App (Java 17+ / 24)
Executive SummaryMEDICARE is an enterprise-grade desktop Point of Sale (POS)
 and inventory management system designed for modern pharmacy operations. 
Developed natively in pure Java, the application features real-time inventory tracking,
 First Expiry, First Out (FEFO) batch management, strict safety interlocks against 
dispensing expired goods, automated text receipt generation, and real-time business intelligence
 analytics.
Problem Statement & System ObjectivesProblem StatementRetail pharmacies face critical challenges
 that threaten patient safety and business revenue:Safety Risks: Accidental sale of expired drugs
 due to manual stock oversight.   Revenue Loss: Spoilage caused by newer batches being sold before
 older ones.   Inaccurate Stock Counts: Stockouts during medical emergencies due to poor tracking.  
 Billing Friction: Slow manual billing and lack of automated invoice receipts.  
 ObjectivesAutomate inventory tracking with strict FEFO batch prioritization.   
Prevent the sale of expired or out-of-stock items using hard program constraints.  
 Showcase production-ready Java architecture using clean Object-Oriented Programming (OOP) without
 external framework dependencies.
Key Features & FunctionalitySecure Authentication: Modal sign-in interface with role-based validation.
   Medicine Catalog CRUD: Comprehensive search and management of drugs by ID, Name, Category,
 Manufacturer, or Batch.   FEFO Sorting Engine: Automatically ranks batches by earliest expiration
 date to minimize spoilage.   Safety Billing Terminal: High-speed POS billing engine with strict
 hard-blocks against expired item checkout.   Automated Receipts: Generates itemized .txt customer
 receipts saved locally.   Business Intelligence: Live dashboard metrics tracking total revenue,
 transaction volume, average ticket size, and top-selling items.
System Architecture & Directory
 StructureMedical Inventory/ ├── data/ │   ├── medicines.csv            # Persistent medicine records │ 

  └── sales.csv                # Persistent sales transaction records ├── receipts/                  
  # Generated customer invoice receipts (.txt) ├── src/ │   ├── Main.java              
  # Application entry point │   ├── TestRunner.java          # Headless automated testing engine │   ├── model/  

                 # Data objects (Item, Medicine, Sale, SaleItem) │   ├── exception/   

 # Custom business logic exceptions │   ├── service/       
          # Core business services (Inventory, Billing, Reports) │   ├── util/                   
 # Utility classes (Date, Validation, File, UITheme) │   └── ui/                     
 # Swing UI frames, dialogs, and custom components └── README.md                   
 # System documentation
Technical Specification & OOP Concepts ShowcaseJava OOP ConceptImplementation in 
MEDICAREEncapsulationPrivate member variables exposed strictly via validated getters and setters. 
  InheritanceCustom UI controls extend Swing primitives (JPanel, JButton); Medicine extends Item. 
  PolymorphismOverridden methods like paintComponent() for custom graphics and getTotalValue().  
 CollectionsHeavy reliance on List, ArrayList, Map, Lambda expressions, and custom Comparator chains.
   Custom ExceptionsDomain-specific error handling via ExpiredMedicineException and
 InsufficientStockException.   File I/OSafe CSV parsing and text output via try-with-resources and
 buffered streams.   6. Core Functional ModulesMedicine Management Panel: Multi-parameter search 
table with visual status badges (IN STOCK, LOW STOCK, EXPIRING SOON, EXPIRED).  
 Inventory & Expiry Control Panel: Categorized tab views with dedicated FEFO sorting, 
low-stock alerts, and one-click restocking.   POS Billing Terminal: Dual-panel layout for quick

 item selection, real-time cart updating, discount/tax calculations, and receipt generation.  
 Sales History & Analytics Panel: Historical sales auditing with time range filters 
(Today, 7 Days, Month, All Time) and top-seller rankings[cite: 1].Dashboard System Shell:
 Real-time digital header clock, KPI metric cards, and stock alert grids[cite: 1].7.
 Verification & TestingThe system includes a headless verification engine in 
TestRunner.java executing 23 automated assertions without opening GUI windows[cite: 1]:
Class & Inheritance Integrity: Verifies class hierarchy and polymorphic total calculations[cite: 1]
.Input Validation: Confirms rejection of invalid prices, empty fie
lds, and duplicate IDs[cite: 1]
.FEFO Mechanics: Tests auto-sorting of batches nearing expiry[cite: 1].Safe
ty Hard-Locks: Verifies
 that expired sales and overselling throw targeted exceptions[cite: 1].Persistence & Reporting: 
Validates file directory creation, receipt generation, and metric calculations[cite: 1].
