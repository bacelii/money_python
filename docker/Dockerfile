# Use the official Python image as the base
FROM python:3.8-slim

# Install system dependencies
RUN apt-get update && \
    apt-get install -y --no-install-recommends \
        build-essential \
        && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists/*

COPY requirements.txt requirements.txt 

# Install Python dependencies
#RUN pip3 install --no-cache-dir -r requirements.txt
RUN pip3 install \
    jupyterlab \
    yfinance \ 
    pandas \
    numpy \
    matplotlib \
    notebook 

# Expose port for Jupyter Notebook
EXPOSE 8888

# Start Jupyter Notebook
CMD ["jupyter", "notebook", "--ip=0.0.0.0", "--port=8888", "--no-browser", "--allow-root","--NotebookApp.token=''"]
