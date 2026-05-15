FROM reodica/tibco.bwce263.debian

# 1. Create a numeric user and group
RUN groupadd -g 1001 tibgrp && \
    useradd -r -u 1001 -g tibgrp tibuser

# 2. Ensure the numeric user owns the BWCE runtime folders
RUN chown -R 1001:1001 /resources /u01 

# 3. Switch to the numeric UID
USER 1001

# 4. Copy the EAR file into the correct BWCE deployment directory 
# and ensure user 1001 owns it
ADD --chown=1001:1001 testApp_1.0.0.ear /resources/addons/ear/
