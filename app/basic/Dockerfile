FROM openstat_base:230917
RUN R -e "install.packages(c('shinybrowser'))"
RUN R -e "install.packages(c('emailjsr'))"

# copy the app to the image
RUN mkdir /root/basic
COPY basic /root/basic

COPY Rprofile.site /usr/lib/R/etc/

EXPOSE 3838

CMD ["R", "-e", "shiny::runApp('/root/basic')"]
