WORKDIR /app

# Copy app files
COPY . /app

# Install dependencies as root
RUN pip install --no-cache-dir -r requirements.txt

# Create a non-root user
RUN groupadd -r app && useradd -r -g app appuser

# Change ownership
RUN chown -R appuser:app /app

# Switch to non-root user
USER appuser

# Expose Streamlit default port
EXPOSE 8501

# Command to run your app
CMD ["streamlit", "run", "app.py"]
