# Utilise l'image officielle Nginx
FROM nginx:latest

# Label pour le projet
LABEL "project"="vprofile-project"
LABEL "author"="Ben Ammar"

# Remove the default Nginx configuration file
RUN rm /etc/nginx/conf.d/default.conf
# Copy the custom Nginx configuration file
COPY nginx.conf /etc/nginx/conf.d/      


