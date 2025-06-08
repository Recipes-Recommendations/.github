# Recipe Recommendations

A comprehensive recipe recommendation platform that helps users discover and explore new recipes using semantic search and machine learning. The platform consists of multiple components that work together to provide an intelligent recipe discovery experience.

## Project Overview

Recipe Recommendations is a full-stack application that uses machine learning to provide intelligent recipe recommendations. The platform processes recipe data, creates semantic embeddings, and serves recommendations through a modern web interface.

## Components

### 1. [createDataset](https://github.com/Recipes-Recommendations/createDataset)
- Processes the RecipeNLP dataset using PySpark
- Implements TF-IDF vectorization for text analysis
- Calculates cosine similarity between recipes
- Identifies similar and different recipes for training
- Outputs processed data in Parquet format

### 2. [trainModel](https://github.com/Recipes-Recommendations/trainModel)
- Fine-tunes a sentence transformer model for recipe embeddings
- Uses LoRA (Low-Rank Adaptation) for efficient training
- Creates semantic embeddings for recipe titles and ingredients
- Pushes the fine-tuned model to Hugging Face Hub

### 3. [createVectorEmbeddings](https://github.com/Recipes-Recommendations/createVectorEmbeddings)
- Generates vector embeddings for recipes using the fine-tuned model
- Stores embeddings in Redis for efficient similarity search
- Provides testing capabilities for the embeddings
- Optimizes vector search for cosine similarity

### 4. [api](https://github.com/Recipes-Recommendations/api)
- FastAPI-based REST API for recipe recommendations
- Implements semantic search using the trained model
- Uses Redis for caching and click tracking
- Containerized with Docker and Kubernetes-ready
- Includes comprehensive API documentation

### 5. [frontend](https://github.com/Recipes-Recommendations/frontend)
- Next.js-based web application
- Modern, responsive user interface
- Implements infinite scroll for recipe results
- Optimized for all screen sizes
- Deployed on Vercel

## Getting Started

Follow these steps to set up the complete Recipe Recommendations platform:

1. **Data Processing**
   ```bash
   # Clone and set up createDataset
   git clone https://github.com/Recipes-Recommendations/createDataset.git
   cd createDataset
   pip install -r requirements.txt
   # Update S3 bucket configuration
   # Run the PySpark job
   ```

2. **Model Training**
   ```bash
   # Clone and set up trainModel
   git clone https://github.com/Recipes-Recommendations/trainModel.git
   cd trainModel
   pip install -r requirements.txt
   # Update model configuration
   # Run the training notebook
   ```

3. **Create Vector Embeddings**
   ```bash
   # Clone and set up createVectorEmbeddings
   git clone https://github.com/Recipes-Recommendations/createVectorEmbeddings.git
   cd createVectorEmbeddings
   pip install -r requirements.txt
   # Update Redis and model configuration
   # Run the embedding generation notebook
   ```

4. **API Setup**
   ```bash
   # Clone and set up the API
   git clone https://github.com/Recipes-Recommendations/api.git
   cd api
   pip install -r requirements.txt
   # Configure environment variables
   # Build and run with Docker
   docker build -t recipe-api .
   docker run -p 8000:8000 recipe-api
   ```

5. **Frontend Development**
   ```bash
   # Clone and set up the frontend
   git clone https://github.com/Recipes-Recommendations/frontend.git
   cd frontend
   npm install
   # Start development server
   npm run dev
   ```

## Deployment

The platform is designed to be deployed on AWS using Kubernetes:

1. Set up an EKS cluster
2. Configure AWS Load Balancer Controller
3. Deploy the API using the provided Kubernetes manifests
4. Deploy the frontend to Vercel
5. Configure DNS and SSL certificates
