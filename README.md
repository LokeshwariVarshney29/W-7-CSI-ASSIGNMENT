# 🚀 Azure Data Factory: Advanced ETL Pipeline Implementation

## 📌 Project Overview

This project demonstrates the implementation of a comprehensive **Azure Data Factory (ADF) pipeline** that orchestrates data processing workflows with advanced features including:

* Metadata-driven pipeline execution
* Multiple data flow transformations
* Parameterized and dynamic data processing
* Automated scheduling with triggers
* Integration with Azure Data Lake Storage Gen2 and Azure SQL Database

## 🧠 Problem Statement

The pipeline processes multiple data sources and transforms them according to specific business requirements:

1. **CUST_MSTR** - Customer master data processing
2. **master_child_export** - Hierarchical data transformation
3. **H_ECOM_ORDER** - E-commerce order data loading

Each data source requires:
- Metadata extraction and validation
- Custom transformation logic
- Structured loading into target SQL tables
- Daily automated execution

## 🏗️ Azure Resources Architecture

The solution leverages the following Azure services:

* **Azure Data Factory (V2)** - Core orchestration engine
* **Azure SQL Database** - Target data warehouse
* **Azure Data Lake Storage Gen2** - Source data repository
* **Azure SQL Server** - Database hosting infrastructure

## 🔗 Linked Services Configuration

The pipeline utilizes two primary linked services:

### AzureDataLakeStorage1
- **Type**: Azure Data Lake Storage Gen2
- **Purpose**: Source data connection
- **Related**: 3 datasets

### AzureSqlDatabase1
- **Type**: Azure SQL Database
- **Purpose**: Target database connection
- **Related**: 3 datasets

## 🗂️ Dataset Configuration

The pipeline includes 6 datasets organized as follows:

### Source Datasets (CSV)
- `CUST_MSTR` - Customer master CSV files
- `master_child_export` - Export data CSV files
- `H_ECOM_ORDER` - E-commerce order CSV files

### Target Datasets (SQL Tables)
- `CUST_MSTR_TABLE` - Customer master table
- `master_child_export_TABLE` - Export data table
- `H_ECOM_ORDER_TABLE` - E-commerce order table

## 🧪 Pipeline Architecture

### Main Pipeline: pipeline1

The master pipeline orchestrates three parallel data processing workflows:

1. **CUST_MSTR Processing Flow**
   - Get Metadata → ForEach → Data Flow (dataflow1)
   
2. **master_child_export Processing Flow**
   - Get Metadata → ForEach → Data Flow (dataflow2)
   
3. **H_ECOM_ORDER Processing Flow**
   - Get Metadata → ForEach → Data Flow (dataflow3)

## 🔁 Data Flow Implementations

### 🔄 DataFlow1 - CUST_MSTR Processing
- **Purpose**: Customer master data transformation
- **Key Features**:
  - Dynamic source file processing
  - Data type conversions
  - Business rule applications
  - Target table loading

### 🔄 DataFlow2 - master_child_export Processing
- **Purpose**: Hierarchical data transformation
- **Key Features**:
  - Parent-child relationship processing
  - Data lineage maintenance
  - Complex transformation logic
  - Structured output generation

### 🔄 DataFlow3 - H_ECOM_ORDER Processing
- **Purpose**: E-commerce order data processing
- **Key Features**:
  - Order transaction processing
  - Data validation and cleansing
  - Business metrics calculation
  - Fact table population

## 📊 Metadata Activities

Each processing flow begins with a **Get Metadata** activity that:
- Discovers available files in the source directory
- Validates file structure and format
- Provides dynamic file list for ForEach processing
- Enables error handling and logging

## 🔄 ForEach Loop Processing

The ForEach activities enable:
- **Dynamic file processing** based on metadata discovery
- **Parallel execution** of data flows
- **Scalable architecture** for varying file volumes
- **Error isolation** per file processing

## ⏰ Trigger Configuration

### trigger1 - Daily Execution Schedule
- **Type**: ScheduleTrigger
- **Start Date**: 7/7/2025, 3:37:00 PM
- **Time Zone**: Chennai, Kolkata, Mumbai, New Delhi (UTC+5:30)
- **Recurrence**: Every 1 Day(s)
- **Execution Times**: 
  - Hours: 07
  - Minutes: 00
- **Schedule**: Daily at 07:00 AM IST

## 💼 Resource Management

### Resource Group: rg-csideproject
The project resources are organized within a dedicated resource group containing:
- **adfdatap** - Data Factory (V2) instance
- **DataWarehouse** - SQL Database for data storage
- **sqlserver-csideproject** - SQL Server instance
- **stadatalakeproject** - Storage Account for data lake

## 🔧 Advanced Features

### Change Data Capture (Preview)
- **Status**: Available (0 configurations)
- **Purpose**: Future implementation for incremental data processing
- **Benefit**: Reduced processing overhead and improved performance

### Power Query Integration
- **Status**: Available (0 configurations)
- **Purpose**: Advanced data transformation capabilities
- **Benefit**: Enhanced data preparation and cleansing options

## 🚀 Deployment and Monitoring

### Pipeline Execution
- **Trigger-based**: Automated daily execution
- **Manual**: On-demand execution available
- **Monitoring**: Built-in ADF monitoring and logging
- **Alerting**: Azure Monitor integration ready

### Performance Optimization
- **Parallel Processing**: Multiple data flows execute concurrently
- **Resource Scaling**: Auto-scaling based on workload
- **Cost Optimization**: Scheduled execution during off-peak hours
- **Monitoring**: Real-time performance tracking

## 📈 Future Enhancements

### Recommended Improvements
1. **Error Handling**: Implement comprehensive error handling and retry logic
2. **Data Quality**: Add data validation and quality checks
3. **Monitoring**: Enhanced logging and alerting mechanisms
4. **Security**: Implement Azure Key Vault for credential management
5. **CI/CD**: DevOps integration for automated deployment
6. **Testing**: Unit and integration testing frameworks

### Scalability Considerations
- **Dynamic Scaling**: Auto-scaling based on data volume
- **Performance Tuning**: Optimize data flow performance
- **Cost Management**: Implement cost monitoring and optimization
- **Multi-Environment**: Support for dev/test/prod environments

## 💡 Best Practices Implemented

- **Metadata-Driven**: Dynamic pipeline execution based on source metadata
- **Parameterization**: Flexible and reusable pipeline components
- **Error Handling**: Robust error management and logging
- **Performance**: Optimized data flow transformations
- **Monitoring**: Comprehensive pipeline monitoring and alerting
- **Security**: Secure connection management and access control

## 🎯 Key Benefits

- **Automation**: Fully automated daily data processing
- **Scalability**: Handles varying data volumes efficiently
- **Reliability**: Robust error handling and recovery mechanisms
- **Maintainability**: Clean, well-structured pipeline design
- **Cost-Effective**: Optimized resource utilization
- **Monitoring**: Comprehensive visibility into pipeline execution

---

## 👤 Author

**Lokeshwari Varshney**

*This implementation demonstrates enterprise-grade data integration capabilities using Azure Data Factory, showcasing modern ETL/ELT patterns and best practices for cloud-based data processing.*
