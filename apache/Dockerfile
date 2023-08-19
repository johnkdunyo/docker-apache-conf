# Use the official Apache HTTP Server image as the base
FROM httpd:latest

# Enable proxy modules
# RUN sed -i '/#LoadModule proxy_module/s/^#//g' /usr/local/apache2/conf/httpd.conf && \
#     sed -i '/#LoadModule proxy_http_module/s/^#//g' /usr/local/apache2/conf/httpd.conf

# Copy your custom httpd.conf
COPY httpd.conf /usr/local/apache2/conf/httpd.conf

# Create directories for sites and logs
RUN mkdir -p /usr/local/apache2/conf/sites/

# Expose port 80
EXPOSE 80
EXPOSE 443

# Start Apache in the foreground
CMD ["httpd", "-D", "FOREGROUND"]
