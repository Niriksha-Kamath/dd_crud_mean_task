FROM node:22
# Set the working directory
WORKDIR /usr/src/app

COPY package*.json ./
COPY package-lock.json .

RUN npm cache clean --force
RUN npm install -g @angular/cli
RUN npm install --legacy-peer-deps

# Copy the entire Angular project to the working directory
COPY . .

# Build the Angular app
RUN ng build

# Expose the Angular app's default port (adjust if necessary)
EXPOSE 8081

# Start the Angular app
CMD ["ng", "serve", "--host", "0.0.0.0", "--port", "8081"]
