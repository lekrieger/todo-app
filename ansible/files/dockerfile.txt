# Verwenden Sie das offizielle Debian-Image als Basis
FROM debian

# Aktualisieren Sie das System und installieren Sie Apache
RUN apt-get update && \
    apt-get install -y apache2 && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists/*

# Starten Sie Apache im Vordergrund
CMD ["apache2ctl", "-D", "FOREGROUND"]

# Öffnen Sie den Port 80 für eingehende Verbindungen
EXPOSE 80
