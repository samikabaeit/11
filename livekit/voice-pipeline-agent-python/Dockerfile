FROM python:3.10-slim

WORKDIR /app

# Install system dependencies (optional: ffmpeg if used)
RUN apt-get update && apt-get install -y ffmpeg && rm -rf /var/lib/apt/lists/*

# Install Python dependencies
COPY requirements.txt .
RUN pip install --no-cache-dir -r requirements.txt

# Copy source code
COPY . .

RUN python3 agent.py download-files

# Run the agent
CMD ["python", "agent.py", "dev"]

