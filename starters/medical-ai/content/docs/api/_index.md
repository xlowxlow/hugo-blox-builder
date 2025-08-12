---
linkTitle: API Reference
title: API Reference
weight: 4
---

# API Reference

Complete reference for the Medical AI REST API. All endpoints require authentication and support JSON request/response formats.

## Authentication

All API requests require authentication using Bearer tokens:

```bash
Authorization: Bearer YOUR_API_KEY
```

To obtain an API key, contact our support team or generate one through the developer portal.

## Base URL

```
https://api.medical-ai.com/v1/
```

## Core Endpoints

### Medical Imaging Analysis

#### POST /analyze/imaging

Analyze medical images using AI models.

**Request:**
```json
{
  "model": "RadiologyAI-Pro",
  "image_data": "base64_encoded_image",
  "metadata": {
    "patient_id": "12345",
    "study_type": "chest_xray",
    "urgency": "routine"
  },
  "options": {
    "confidence_threshold": 0.8,
    "return_annotations": true
  }
}
```

**Response:**
```json
{
  "analysis_id": "analysis_001",
  "status": "completed",
  "timestamp": "2023-10-24T10:30:00Z",
  "results": {
    "findings": [
      {
        "finding": "pneumonia",
        "confidence": 0.92,
        "location": {
          "x": 150,
          "y": 200,
          "width": 80,
          "height": 60
        },
        "severity": "moderate"
      }
    ],
    "overall_assessment": "Abnormal findings detected",
    "recommendations": [
      "Clinical correlation recommended",
      "Consider antibiotic therapy"
    ]
  }
}
```

### Clinical Decision Support

#### POST /analyze/clinical

Get treatment recommendations based on patient data.

**Request:**
```json
{
  "patient_data": {
    "age": 65,
    "gender": "male",
    "symptoms": ["chest_pain", "shortness_of_breath"],
    "vital_signs": {
      "blood_pressure": "140/90",
      "heart_rate": 88,
      "temperature": 98.6
    },
    "medical_history": ["hypertension", "diabetes"],
    "current_medications": ["metformin", "lisinopril"]
  },
  "analysis_type": "diagnosis_support"
}
```

**Response:**
```json
{
  "analysis_id": "clinical_001",
  "differential_diagnosis": [
    {
      "condition": "myocardial_infarction",
      "probability": 0.75,
      "urgency": "high"
    },
    {
      "condition": "pulmonary_embolism",
      "probability": 0.68,
      "urgency": "high"
    }
  ],
  "recommended_tests": [
    "ECG",
    "Troponin levels",
    "D-dimer"
  ],
  "treatment_suggestions": [
    {
      "medication": "aspirin",
      "dosage": "325mg",
      "frequency": "once"
    }
  ]
}
```

### Natural Language Processing

#### POST /analyze/text

Extract insights from clinical text.

**Request:**
```json
{
  "text": "Patient presents with acute onset chest pain radiating to left arm. History of smoking and hypertension. Physical exam reveals diaphoresis and elevated blood pressure.",
  "analysis_types": ["entities", "sentiment", "summary"],
  "medical_specialty": "cardiology"
}
```

**Response:**
```json
{
  "analysis_id": "nlp_001",
  "entities": [
    {
      "text": "chest pain",
      "label": "SYMPTOM",
      "confidence": 0.95
    },
    {
      "text": "hypertension",
      "label": "CONDITION",
      "confidence": 0.98
    }
  ],
  "summary": "Acute chest pain with cardiovascular risk factors",
  "sentiment": {
    "urgency": "high",
    "severity": "moderate"
  }
}
```

## Model Management

### GET /models

List available AI models.

**Response:**
```json
{
  "models": [
    {
      "id": "RadiologyAI-Pro",
      "name": "Radiology AI Pro",
      "version": "2.1.0",
      "specialty": "radiology",
      "status": "active",
      "accuracy": 0.952
    },
    {
      "id": "PathologyVision",
      "name": "Pathology Vision",
      "version": "1.8.3",
      "specialty": "pathology",
      "status": "active",
      "accuracy": 0.978
    }
  ]
}
```

### GET /models/{model_id}

Get detailed information about a specific model.

## Rate Limiting

API requests are rate limited to ensure fair usage:

- **Free Tier**: 100 requests per hour
- **Professional**: 1,000 requests per hour
- **Enterprise**: 10,000 requests per hour
- **Custom**: Unlimited with dedicated infrastructure

## Error Handling

The API uses standard HTTP status codes:

- **200**: Success
- **400**: Bad Request - Invalid parameters
- **401**: Unauthorized - Invalid API key
- **403**: Forbidden - Insufficient permissions
- **429**: Too Many Requests - Rate limit exceeded
- **500**: Internal Server Error

**Error Response Format:**
```json
{
  "error": {
    "code": "INVALID_IMAGE_FORMAT",
    "message": "Image must be in JPEG, PNG, or DICOM format",
    "details": {
      "provided_format": "gif",
      "supported_formats": ["jpeg", "png", "dicom"]
    }
  }
}
```

## SDKs and Libraries

We provide official SDKs for popular programming languages:

- **Python**: `pip install medical-ai-sdk`
- **JavaScript/Node.js**: `npm install medical-ai-sdk`
- **Java**: Available via Maven Central
- **C#/.NET**: Available via NuGet
- **R**: `install.packages("medicalai")`

## Webhooks

Configure webhooks to receive real-time notifications:

```json
{
  "webhook_url": "https://your-system.com/webhooks/medical-ai",
  "events": ["analysis_completed", "error_occurred"],
  "secret": "your_webhook_secret"
}
```

## Testing

Use our sandbox environment for testing:

```
https://sandbox-api.medical-ai.com/v1/
```

Test API keys are available in the developer portal.