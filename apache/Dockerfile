# Use the official Apache HTTP Server image as the base
FROM httpd:latest

# Enable proxy modules
# RUN sed -i '/#LoadModule proxy_module/s/^#//g' /usr/local/apache2/conf/httpd.conf && \
#     sed -i '/#LoadModule proxy_http_module/s/^#//g' /usr/local/apache2/conf/httpd.conf

# Copy your custom httpd.conf
COPY httpd.conf /usr/local/apache2/conf/httpd.conf

# Create directories for sites
RUN mkdir -p /usr/local/apache2/conf/sites/

# Create directories for ssl
RUN mkdir -p /usr/local/apache2/conf/ssl/

# Copy and make the passphrase script executable
COPY passphrase_script.sh /usr/local/apache2/conf/ssl/passphrase_script.sh
RUN chmod +x /usr/local/apache2/conf/ssl/passphrase_script.sh

# Expose port 80
EXPOSE 80
EXPOSE 443

# Start Apache in the foreground
CMD ["httpd", "-D", "FOREGROUND"]
