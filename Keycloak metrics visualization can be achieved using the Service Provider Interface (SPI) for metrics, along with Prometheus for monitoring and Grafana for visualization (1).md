# Keycloak Metrics with Prometheus and Grafana

  
  
  
  
  
  
  
  
  
  
  
  
  
  

## MADE BY: MANISH YADAV

  

![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXcnaEvZyjACZDi1neeAC-_eCZQbz1E5sfYI59MHia-Td00dutIaHg-ZipXMntK53008or5LdBFHQPQqlhrknzD4HA8i4rZ0YwA_cwFWEBsp1JQSTKI0QGJsgI1v1A4SL5vcuJyGiw?key=ICzLerXjukSgelnUIdp7Y9vf)

  
  
  
  
  
  
  
  

## Table of Content

  
  

[1). Technical Requirements: 4](https://docs.google.com/document/d/1qhJMMNI1HGZjkAighs4yxuXCGvYL1Eg96fdpnTIde5w/edit?tab=t.0#heading=h.p5teib7ddj8w)

[1.1: Operating System: 4](https://docs.google.com/document/d/1qhJMMNI1HGZjkAighs4yxuXCGvYL1Eg96fdpnTIde5w/edit?tab=t.0#heading=h.ffu3195h0l6v)

[1.2: Network Configuration: 4](https://docs.google.com/document/d/1qhJMMNI1HGZjkAighs4yxuXCGvYL1Eg96fdpnTIde5w/edit?tab=t.0#heading=h.ysqnuq5kk7ng)

[1.3: Software & Tools: 4](https://docs.google.com/document/d/1qhJMMNI1HGZjkAighs4yxuXCGvYL1Eg96fdpnTIde5w/edit?tab=t.0#heading=h.7t4u289xdb97)

[1.4: Server Resources: 4](https://docs.google.com/document/d/1qhJMMNI1HGZjkAighs4yxuXCGvYL1Eg96fdpnTIde5w/edit?tab=t.0#heading=h.wh1qahtwhswp)

[2). Knowledge Requirements: 5](https://docs.google.com/document/d/1qhJMMNI1HGZjkAighs4yxuXCGvYL1Eg96fdpnTIde5w/edit?tab=t.0#heading=h.lutzs9u2fk5v)

[2.1: Basic Linux Commands: 5](https://docs.google.com/document/d/1qhJMMNI1HGZjkAighs4yxuXCGvYL1Eg96fdpnTIde5w/edit?tab=t.0#heading=h.k61yhlk7e97e)

[2.2: Containerization Basics: 5](https://docs.google.com/document/d/1qhJMMNI1HGZjkAighs4yxuXCGvYL1Eg96fdpnTIde5w/edit?tab=t.0#heading=h.ydf75sxxgcrf)

[2.3: Keycloak Basics: 5](https://docs.google.com/document/d/1qhJMMNI1HGZjkAighs4yxuXCGvYL1Eg96fdpnTIde5w/edit?tab=t.0#heading=h.mveuub3q47db)

[2.4: Database Knowledge: 5](https://docs.google.com/document/d/1qhJMMNI1HGZjkAighs4yxuXCGvYL1Eg96fdpnTIde5w/edit?tab=t.0#heading=h.u16ke66jwawi)

[2.5: Monitoring Tools: 5](https://docs.google.com/document/d/1qhJMMNI1HGZjkAighs4yxuXCGvYL1Eg96fdpnTIde5w/edit?tab=t.0#heading=h.nwnplnjgooyx)

[2.6: LDAP Concepts: 5](https://docs.google.com/document/d/1qhJMMNI1HGZjkAighs4yxuXCGvYL1Eg96fdpnTIde5w/edit?tab=t.0#heading=h.cznxsvjkzr2n)

[3). Keycloak Metrics SPI Setup 6](https://docs.google.com/document/d/1qhJMMNI1HGZjkAighs4yxuXCGvYL1Eg96fdpnTIde5w/edit?tab=t.0#heading=h.zi9ow6db0kep)

[3.1: Download and Extract Metrics SPI: 6](https://docs.google.com/document/d/1qhJMMNI1HGZjkAighs4yxuXCGvYL1Eg96fdpnTIde5w/edit?tab=t.0#heading=h.57dtl3sclk7)

[4). Install Java (OpenJDK 21): 7](https://docs.google.com/document/d/1qhJMMNI1HGZjkAighs4yxuXCGvYL1Eg96fdpnTIde5w/edit?tab=t.0#heading=h.u9s5sjpz3r05)

[5). Build the SPI: 7](https://docs.google.com/document/d/1qhJMMNI1HGZjkAighs4yxuXCGvYL1Eg96fdpnTIde5w/edit?tab=t.0#heading=h.4l5yc2xrawla)

[6). Run PostgreSQL for Keycloak: 8](https://docs.google.com/document/d/1qhJMMNI1HGZjkAighs4yxuXCGvYL1Eg96fdpnTIde5w/edit?tab=t.0#heading=h.g4e7fd4z6gqr)

[7). Run Keycloak with the Custom SPI: 8](https://docs.google.com/document/d/1qhJMMNI1HGZjkAighs4yxuXCGvYL1Eg96fdpnTIde5w/edit?tab=t.0#heading=h.mifgbtbsq3fr)

[8). Verify Setup: 9](https://docs.google.com/document/d/1qhJMMNI1HGZjkAighs4yxuXCGvYL1Eg96fdpnTIde5w/edit?tab=t.0#heading=h.sd6ge5jju95v)

[9). Steps to Create Realm, Client, and Users in Keycloak and Enable Metrics Listener 10](https://docs.google.com/document/d/1qhJMMNI1HGZjkAighs4yxuXCGvYL1Eg96fdpnTIde5w/edit?tab=t.0#heading=h.e03tfbssi9t5)

[9.1: Access Keycloak Admin Console 10](https://docs.google.com/document/d/1qhJMMNI1HGZjkAighs4yxuXCGvYL1Eg96fdpnTIde5w/edit?tab=t.0#heading=h.d0z6lvf8ghe)

[9.2: Create a Realm 11](https://docs.google.com/document/d/1qhJMMNI1HGZjkAighs4yxuXCGvYL1Eg96fdpnTIde5w/edit?tab=t.0#heading=h.8hqreh3rp9cp)

[9.3: Create a Client 12](https://docs.google.com/document/d/1qhJMMNI1HGZjkAighs4yxuXCGvYL1Eg96fdpnTIde5w/edit?tab=t.0#heading=h.5dv3soqnpqgs)

[9.5: Create Users 13](https://docs.google.com/document/d/1qhJMMNI1HGZjkAighs4yxuXCGvYL1Eg96fdpnTIde5w/edit?tab=t.0#heading=h.46syrynm7bjv)

[9.6: To set a password for the user 14](https://docs.google.com/document/d/1qhJMMNI1HGZjkAighs4yxuXCGvYL1Eg96fdpnTIde5w/edit?tab=t.0#heading=h.873yk22bvv7p)

[9.7: Enable Metrics Listener 14](https://docs.google.com/document/d/1qhJMMNI1HGZjkAighs4yxuXCGvYL1Eg96fdpnTIde5w/edit?tab=t.0#heading=h.9zg56jlt8tig)

[10). Create a Prometheus Configuration File 15](https://docs.google.com/document/d/1qhJMMNI1HGZjkAighs4yxuXCGvYL1Eg96fdpnTIde5w/edit?tab=t.0#heading=h.kqt9n4i4hhta)

[11). Run Prometheus as a Docker/Podman Container 16](https://docs.google.com/document/d/1qhJMMNI1HGZjkAighs4yxuXCGvYL1Eg96fdpnTIde5w/edit?tab=t.0#heading=h.x7drd06oja7x)

[12). Access Prometheus 16](https://docs.google.com/document/d/1qhJMMNI1HGZjkAighs4yxuXCGvYL1Eg96fdpnTIde5w/edit?tab=t.0#heading=h.7s9s4kk41bzn)

[13). Start the Grafana Container 17](https://docs.google.com/document/d/1qhJMMNI1HGZjkAighs4yxuXCGvYL1Eg96fdpnTIde5w/edit?tab=t.0#heading=h.fq7q1et266h8)

[14). Access Grafana 17](https://docs.google.com/document/d/1qhJMMNI1HGZjkAighs4yxuXCGvYL1Eg96fdpnTIde5w/edit?tab=t.0#heading=h.1hob0lwdksz5)

[15). Add Data Source in Grafana 18](https://docs.google.com/document/d/1qhJMMNI1HGZjkAighs4yxuXCGvYL1Eg96fdpnTIde5w/edit?tab=t.0#heading=h.ivp9kmrpwlq2)

[16). Create and Import a Dashboard in Grafana 19](https://docs.google.com/document/d/1qhJMMNI1HGZjkAighs4yxuXCGvYL1Eg96fdpnTIde5w/edit?tab=t.0#heading=h.eo1m8qsxqwt3)

[17). Deploying the Ldap389 Directory Server 20](https://docs.google.com/document/d/1qhJMMNI1HGZjkAighs4yxuXCGvYL1Eg96fdpnTIde5w/edit?tab=t.0#heading=h.m72017ir14gq)

[18). Accessing the LDAP Container 20](https://docs.google.com/document/d/1qhJMMNI1HGZjkAighs4yxuXCGvYL1Eg96fdpnTIde5w/edit?tab=t.0#heading=h.yt72gbganiyl)

[19). Configuring the Directory Backend 20](https://docs.google.com/document/d/1qhJMMNI1HGZjkAighs4yxuXCGvYL1Eg96fdpnTIde5w/edit?tab=t.0#heading=h.677i8ljntiab)

[20). Defining the LDAP Directory Structure 21](https://docs.google.com/document/d/1qhJMMNI1HGZjkAighs4yxuXCGvYL1Eg96fdpnTIde5w/edit?tab=t.0#heading=h.2tjz5ec97d0z)

[21). Adding User Entries 22](https://docs.google.com/document/d/1qhJMMNI1HGZjkAighs4yxuXCGvYL1Eg96fdpnTIde5w/edit?tab=t.0#heading=h.25w4f244hbmm)

[22). Verifying LDAP Entries 23](https://docs.google.com/document/d/1qhJMMNI1HGZjkAighs4yxuXCGvYL1Eg96fdpnTIde5w/edit?tab=t.0#heading=h.d3i46so9wyij)

[23). Configuring User Federation in Keycloak 23](https://docs.google.com/document/d/1qhJMMNI1HGZjkAighs4yxuXCGvYL1Eg96fdpnTIde5w/edit?tab=t.0#heading=h.erywyparg360)

[23.1: Access the Keycloak Admin Console: 23](https://docs.google.com/document/d/1qhJMMNI1HGZjkAighs4yxuXCGvYL1Eg96fdpnTIde5w/edit?tab=t.0#heading=h.mfyzlvkgskv6)

[23.2: Enable LDAP Federation: 23](https://docs.google.com/document/d/1qhJMMNI1HGZjkAighs4yxuXCGvYL1Eg96fdpnTIde5w/edit?tab=t.0#heading=h.pd7fdid96m8g)

[23.3:  Configure LDAP Provider: 23](https://docs.google.com/document/d/1qhJMMNI1HGZjkAighs4yxuXCGvYL1Eg96fdpnTIde5w/edit?tab=t.0#heading=h.b4q591wm69sa)

[23.4: Synchronize Users: 24](https://docs.google.com/document/d/1qhJMMNI1HGZjkAighs4yxuXCGvYL1Eg96fdpnTIde5w/edit?tab=t.0#heading=h.br0vh1zfqidy)

[24).  User Login with LDAP in Keycloak 24](https://docs.google.com/document/d/1qhJMMNI1HGZjkAighs4yxuXCGvYL1Eg96fdpnTIde5w/edit?tab=t.0#heading=h.x1l6io6pdmep)

  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  

## Overview of the Document:

This document provides a step-by-step guide to setting up Keycloak with custom SPI (Service Provider Interface) metrics, integrating PostgreSQL as the database, and configuring Prometheus and Grafana for monitoring. It also outlines the setup of an LDAP server using 389 Directory Server and its integration with Keycloak for user authentication. The guide covers the installation and configuration of necessary services like Podman, Keycloak, PostgreSQL, Prometheus, Grafana, and LDAP server, along with configuring various monitoring and management features.

  
  

# 1). Technical Requirements:

## 1.1: Operating System:

*   A Linux-based OS (CentOS, RHEL, or Ubuntu). Ensure sudo or root access.
    

## 1.2: Network Configuration:

*   A stable network connection for downloading packages or tools unless an offline setup is planned.
    

## 1.3: Software & Tools:

*   Podman or Docker: For containerized deployments.
    
*   Keycloak: The authentication and authorization tool.
    
*   PostgreSQL: Database integration for Keycloak.
    
*   Prometheus: For metrics monitoring.
    
*   Grafana: For data visualization and dashboards.
    
*   LDAP Server (389 Directory Server): For directory services and authentication.
    

## 1.4: Server Resources:

*   Minimum 8 GB RAM and 40 GB disk space recommended.
    
*   Proper storage allocation for database and logs.
    

  
  
  

# 2). Knowledge Requirements:

## 2.1: Basic Linux Commands:

*   Familiarity with terminal operations, file navigation, and user privileges.
    

## 2.2: Containerization Basics:

*   Understanding of containerized environments using Podman or Docker.
    

##            2.3: Keycloak Basics: 

*   Familiarity with Keycloak realms, clients, users, and SPI     configuration.
    

##           2.4: Database Knowledge:

*    Understanding PostgreSQL basics, including creating databases and configuring connections.          
    

##           2.5: Monitoring Tools:

*   Overview of Prometheus for collecting metrics and Grafana for
    

            creating  dashboards.

## 2.6: LDAP Concepts:

*   Knowledge of Lightweight Directory Access Protocol (LDAP) and its use in authentication.
    

  
  

  
  
  
  
  
  

# 3). Keycloak Metrics SPI Setup

## 3.1: Download and Extract Metrics SPI:

*   Use the GitHub link to download the ZIP file for the Keycloak Metrics SPI: [https://github.com/aerogear/keycloak-metrics-spi?ref=blog.elest.io](https://github.com/aerogear/keycloak-metrics-spi?ref=blog.elest.io)
    

  

*   Navigate to the directory where the SPI ZIP file is downloaded.
    

| $ cd filename |
| --- |

  

*   Extract the ZIP file to prepare the project for building.
    

| $ unzip keycloak-metrics-spi-master.zip |
| --- |

  
  

*   Navigate to the directory of the unzipped file.
    

| $ cd keycloak-metrics-spi-master/ |
| --- |

  
  

*   Update the system package index by running the following command:
    

| $ sudo apt update |
| --- |

  
  
  
  
  
  
  
  
  
  
  

# 4). Install Java (OpenJDK 21):

*   Install the OpenJDK 21 development kit by running the following command:
    

| $ sudo apt install openjdk-21-jdk |
| --- |

  

*   Configure the default Java version by running the following command:
    

| $ update-alternatives --config java |
| --- |

  

*   Set the JAVA\_HOME environment variable by running the following command:
    

| $ export JAVA_HOME=/usr/lib/jvm/java-21-openjdk-amd64 |
| --- |

  

*   Permanently set the JAVA\_HOME environment variable by appending it to your ~/.bashrc file. Run the following command:
    

  

| $ echo "export JAVA_HOME=/usr/lib/jvm/java-21-openjdk-amd64" >> ~/.bashrc |
| --- |

  

# 5). Build the SPI:

*   Navigate to the project directory and use Gradle to build the project.
    

  

| $ ./gradlew jar |
| --- |

  

*   List the contents of the build/libs/ directory to confirm that the .jar file has been successfully created. Use the following command:
    

| $ ls build/libs/ |
| --- |

  

# 6). Run PostgreSQL for Keycloak:

*   Use Podman to run a PostgreSQL container for Keycloak with the required configurations.
    

  

| $ podman run -d --name keycloak-postgres   --network keycloak-net   -e POSTGRES_USER=keycloak   -e POSTGRES_PASSWORD=manish123   -e POSTGRES_DB=keycloak   -p 5432:5432   postgres:15 |
| --- |

  
  

*   podman run: Runs a new container using Podman.
    
*   \-d: Runs the container in detached mode (in the background).
    
*   \--name keycloak-postgres: Names the container keycloak-postgres.
    
*   \--network keycloak-net: Connects the container to the keycloak-net network.
    
*   \-e POSTGRES\_USER=keycloak: Sets the database username as keycloak.
    
*   \-e POSTGRES\_PASSWORD=manish123: Sets the database password as manish123.
    
*   \-e POSTGRES\_DB=keycloak: Creates a PostgreSQL database named keycloak.
    
*   \-p 5432:5432: Maps port 5432 on the host to port 5432 in the container for database access.
    
*   postgres:15: Specifies the PostgreSQL image version 15 to use.
    

  
  
  
  
  
  
  
  
  
  
  
  
  

# 7). Run Keycloak with the Custom SPI: 

*   Run the Keycloak container with metrics enabled (enable=true), and then mount the SPI JAR file to the Keycloak container's providers directory.
    

  

| $ podman run -d --name keycloak   --network keycloak-net   -e KEYCLOAK_ADMIN=admin   -e KEYCLOAK_ADMIN_PASSWORD=admin   -e KC_DB=postgres   -e KC_DB_URL=jdbc:postgresql://keycloak-postgres/keycloak   -e KC_DB_USERNAME=keycloak   -e KC_DB_PASSWORD=manish123   -e KC_METRICS_ENABLED=true   -v /home/manish/Downloads/keycloak-metrics-spi-master/build/libs/keycloak-metrics-spi-6.0.1-SNAPSHOT.jar:/opt/keycloak/providers/keycloak-metrics-spi.jar:Z   -p 8080:8080   quay.io/keycloak/keycloak:24.0.5 start-dev |
| --- |

  

podman run: Runs a new container using Podman.

\-d: Runs the container in detached mode (in the background).

\--name keycloak: Names the container keycloak.

\--network keycloak-net: Connects the container to the keycloak-net network.

\-e KEYCLOAK\_ADMIN=admin: Sets the Keycloak admin username as admin.

\-e KEYCLOAK\_ADMIN\_PASSWORD=admin: Sets the Keycloak admin password as admin.

\-e KC\_DB=postgres: Specifies that Keycloak will use PostgreSQL as its database.

\-e KC\_DB\_URL=jdbc:postgresql://keycloak-postgres/keycloak: Specifies the PostgreSQL database URL, connecting to keycloak-postgres container.

\-e KC\_DB\_USERNAME=keycloak: Sets the PostgreSQL username for Keycloak as keycloak.

\-e KC\_DB\_PASSWORD=manish123: Sets the PostgreSQL password for Keycloak as manish123.

\-e KC\_METRICS\_ENABLED=true: Enables Keycloak metrics collection.

\-v /home/manish/Downloads/keycloak-metrics-spi-master/build/libs/keycloak-metrics-spi-6.0.1-SNAPSHOT.jar:/opt/keycloak/providers/keycloak-metrics-spi.jar:Z: Mounts the keycloak-metrics-spi-6.0.1-SNAPSHOT.jar file from the host to the Keycloak container, making the custom metrics provider available.

\-p 8080:8080: Maps port 8080 on the host to port 8080 in the container for accessing Keycloak.

quay.io/keycloak/keycloak:24.0.5: Specifies the Keycloak Docker image version 24.0.5 to use.

start-dev: Starts Keycloak in development mode.

  
  
  
  

*   Access the Keycloak Container's Bash Shell.
    

  

| $ podman exec -it keycloak bash |
| --- |

  
  
  

*   Exit the bash shell inside the Keycloak container after verifying the presence of the keycloak-metrics-spi.jar file in the correct directory.
    

  

| $ cd opt/keycloak/providers/ |
| --- |

  
  

| $ lskeycloak-metrics-spi.jar  README.md |
| --- |

  
  

| $ exit |
| --- |

  
  

# 8). Verify Setup:

*   Access the Keycloak admin page at http://localhost:8080 and configure realms, clients, and users. { Figure 8\[A\] Access Keycloak admin login page}
    
*   Enable metrics listeners and verify metrics at /realms/{realm\_name}/metrics. { Figure8\[B\] Enable metrics listeners}
    

Figure 8\[A\] Access Keycloak admin login page

![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXcjQpfK9giceeCOmR0tV4nZvJt7NsuW9up0ZARhWJ0tNTfcul7NHzCy7zeCMCuF17ejjuZTt0bTMh7PIO7wgvMutS44mVWNQsg3G8BFzN9o7T-8jhctUpBqvYl2e5WSXrHHnRiZ7A?key=ICzLerXjukSgelnUIdp7Y9vf)

Figure8\[B\] Enable metrics listeners

![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXd5S899rQyYBUdHCwUChu0C_D9hY6ep_UnfORpq09Ei1azsg6MaJfB5zd0ulsI4Vs-Oc5-zRYnFD4PcRPUdi772lZdhDqoLn96FJLP1i1r_7V2v0SpPEXF0NowycDcYVpY-5eeX?key=ICzLerXjukSgelnUIdp7Y9vf)

  

# 9). Steps to Create Realm, Client, and Users in Keycloak and Enable Metrics Listener

## 9.1: Access Keycloak Admin Console

*   Open a web browser and go to the Keycloak Admin Console, typically available at: {Figure 9.1 Access Keycloak admin login page}
    

  

| http://<keycloak-host>:8080/ |
| --- |

  
  

Figure 9.1 Access Keycloak admin login page

![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXdggWl2p6VFcI-vVAZEDhynTBFQf1RI_I9RQmVs-698dlKhnU70Ey4AX41IX2txSaUoa_v41X8y_gOr-QqWXXYFjYCHeEPh8zGUpo4S_Awas-A0NEcQb-guvZPAJbYXHRhQY4bTmQ?key=ICzLerXjukSgelnUIdp7Y9vf)

##          9.2: Create a Realm

*   In the Keycloak Admin Console, click on the Master dropdown in the top-left corner. {Figure 9.2\[A\] Listing Realms in Keycloak}
    
*   Select Add realm. { 
    
*   Provide the Name for the new realm (e.g., demo) and click Create. {Figure 9.2\[B\] Creating a Realm in Keycloak}
    

  
  
  
  

Figure 9.2\[A\] Listing Realms in Keycloak

![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXeLM-0ttT8vIevvWT5OW9wvvFXyE2ZtfmFZjRK4vCDbb2oEmA2WjpALqrKrsRzNneyPjGd3p2HhH99tb83eIVA4_CmUnqgwoxFIGzjfp6zRCUUfKZGR-St4lL2C1Um27Ftu1wDVlg?key=ICzLerXjukSgelnUIdp7Y9vf)

  

Figure 9.2\[B\] Creating a Realm in Keycloak

![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXdQzKRMlJt66-VjCyhITx8pq5OE7lPxlGc6zfPO5wgSJlcPIV8aWKKfmU0ysvPAPbzygQosCQt9aSuXo5eW36rD41P_YmaKzhzmxgFa6uj80bP35WNsAfFzLyVjNVZGoal4woMvFw?key=ICzLerXjukSgelnUIdp7Y9vf)

Figure 9.2\[C\] Access Realms in Keycloak

![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXfXZx4CRNnMw8a2jQl7B9oDbM5nCVeU7IkwKIbxDcjPT48RmMQQsxILlC4q4uAHb8TUO-TRqTO8TrXeyCs79PR6AFaiQz-LiE9mV2Stl5OC-PgpiDJanJFakyE06N1sz9j4xvwt?key=ICzLerXjukSgelnUIdp7Y9vf)

  
  

##          9.3: Create a Client

*    Navigate to the new realm by selecting it from the dropdown. 
    
*   In the left-hand menu, click on Clients and then click Create. {Figure 9.3\[A\] Click on client section}
    
*   Provide the following details:
    

*   Client ID: A unique identifier for the client (e.g., my-client).
    
*   Client Protocol: Select openid-connect.
    
*   Click Save.{Figure 9.3\[B\] Creating a Client in a Realm}
    

  

Figure 9.3\[A\] Click on client section

![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXfq5T0-H245RbtRvHvL4VKPoUzS8ccuDrh3sLsPoSagZp3LnRnks-YphH_1sodwIo1cluXC89xzfjnwCMkul4aw9MKASmp-ifmkRB_Q5edF9_qDk90M7IljNmSrh_HqtQLdO8eJBw?key=ICzLerXjukSgelnUIdp7Y9vf)

Figure 9.3\[B\] Creating a Client in a Realm

![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXf1BC-kICJue9z04s1wIOaHmYd1QIaJLAI4ywpQoRJ6L9qE4PRr795ztmSON1_Cr7uIy_pwU3YMtJntmIW52CphbUIyLKx91l6z_y8OR71fVP8A9UMQORahhg_LDf6zoT5iZyPqGg?key=ICzLerXjukSgelnUIdp7Y9vf)

  
  
  
  
  
  
  
  
  

Figure 9.3\[C\] Configuring Client Details

![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXfBmybqlWV1WEgKiunRvfBe3F3mX2-2QmMXmjO-FyQ5lqGhqUl8yKhqEdKyUHjiayfFCjckmaJVS-iSjmAnuTrhYLIfawH3Q1suPndm5nje--u4KVmWjAuYfAwrpP3u4fTFeW4I?key=ICzLerXjukSgelnUIdp7Y9vf)

         9.4: Configure the client:

*   Under the Settings tab, set the Access Type (e.g., confidential).
    
*   Click Save.
    

  

##        9.5: Create Users

*   In the left-hand menu, click Users and then Add user.
    
*   Fill in the required fields:
    

*   Username: Enter the username for the user.
    
*   Optionally, provide additional details like Email, First Name, and Last Name.
    
*   Click Save.
    

  
  

Figure 9.5\[A\]: List user in Realm

![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXc7b9wde0hVagSK1-xAA4eJvrbSM3MnofnFOTF-52Iu6prktg5Ts-1R8dt2GryOjhq1mXhH3igwCDoFw_p4CARwSqJOGQK6eAo_s0YOoPv961WSyxAdenIi8PBq4XSl2p4_yjp4MQ?key=ICzLerXjukSgelnUIdp7Y9vf)

Figure 9.3\[B\]  Create Users in a Realm

![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXeyJZ2n2nHwKqwnmw5JqxLU5vm9lMqLC471XlOoD9NlBwnUT_fb1aXSlwlG5eg64pspNBYe86a0-h-YQ-jVY7cKoeHnnTSR7Uokjf_NUrfdWgzcelrB2IumM94eZu6rPowHfbw-?key=ICzLerXjukSgelnUIdp7Y9vf)

##       9.6: To set a password for the user

*   Navigate to the Credentials tab.
    
*   Enter the desired password in the Password and Password Confirmation fields.
    
*   Enable Temporary if you want the user to change the password on their next login. Disable it if the password is permanent.
    
*   Click Set Password.
    

  
  
  

Figure 9.6: To set a password for the user

![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXfLt5H5JBN2DR2NtFNtqy2V_1__gaVszQQyesbdXLdkhB6NmXG_ZGRz5smbPSxxXCVq3WThaC1gcN7HXZusQTtASWv-FkosGYdwNm8CSl5CCTOTTSgQFbJIWiBpD-UZLDLsKuta4A?key=ICzLerXjukSgelnUIdp7Y9vf)

##      9.7: Enable Metrics Listener

*    Navigate to the Realm Settings section in the left-hand menu of the Admin Console.
    
*   Click on the Events tab.
    
*   Enable the Admin Events and User Events checkboxes to start tracking metrics for administrative and user activities.
    
*   Save the settings.
    

Figure 9.7: Enable Metrics Listener

![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXeNVUUDsCrwk0VVUs7Zou4KW6dAxSu9OsjkanIahwoykJwNBu3sScLQu5pxDD6ANClxiAwJwzWJ8f_HlkpuO-pbJdf6rJAXM90ZKx3YyBbwid_j5aqlPANdj_o8H9DT6LqtQwtqZg?key=ICzLerXjukSgelnUIdp7Y9vf)

  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  

Integration of Prometheus and Grafana for Keycloak Metrics Monitoring

This section provides a step-by-step guide to configure Prometheus for scraping Keycloak metrics and visualize them in Grafana. This process includes creating configuration files, running containers, and setting up monitoring dashboards.

  

# 10). Create a Prometheus Configuration File

Prometheus requires a configuration file (prometheus.yml) to define the scraping jobs. This file specifies how Prometheus collects metrics from Keycloak.

  

*   Open a terminal and create the file:
    

  

| $ vim prometheus.yml |
| --- |

  

*   Add the following configuration to scrape Keycloak metrics:
    

  

| global:  scrape_interval: 15s  # The interval at which metrics will be collectedscrape_configs:  - job_name: 'keycloak'  # Name of the job    metrics_path: '/realms/master/metrics'  # Keycloak metrics endpoint    static_configs:      - targets: ['192.168.122.74:8080']  # Keycloak's IP and port |
| --- |

  

*   Save and exit the file.
    

  

# 11). Run Prometheus as a Docker/Podman Container

*   Start the Prometheus container with the configuration file mounted:
    

| $ podman run -d --name prometheus \  --network keycloak-net \  -p 9090:9090 \  -v /home/manish/prometheus.yml:/etc/prometheus/prometheus.yml:Z \  docker.io/prom/prometheus |
| --- |

*   podman run: Starts a new container based on the specified image.
    
*   \-d: Run the container in detached mode (in the background).
    
*   \--name prometheus: Assigns the name prometheus to the container for easier identification.
    
*   \--network keycloak-net: Connects the container to the keycloak-net network, allowing it to communicate with other containers on the same network (e.g., Keycloak).
    
*   \-p 9090:9090: Maps port 9090 on the host to port 9090 in the container, exposing the Prometheus web interface on the host machine.
    
*   \-v /home/manish/prometheus.yml:/etc/prometheus/prometheus.yml:ZMounts the file /home/manish/prometheus.yml from the host to /etc/prometheus/prometheus.yml inside the container.
    
*   The :Z option sets proper SELinux permissions for shared volumes in Podman environments.
    

*   [docker.io/prom/prometheus](http://docker.io/prom/prometheus): Specifies the container image to use (prom/prometheus from Docker Hub).
    

  

*   Verify Prometheus is running:
    

| $ podman ps |
| --- |

  
  

# 12). Access Prometheus

*   Open your web browser and navigate to:
    

| http://localhost:9090 |
| --- |

  

*   Use the Prometheus web interface to ensure metrics are being scraped correctly.
    

Figure 12: Access Prometheus and check status up or down

![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXcIBztBzQ-lzJBL_Om250z4jjn5heJCbCprE4JKr7ZXz7b8VCq7FrJZMUVhusQVYwF7PzqXV3RR249fqLMqzCi2NJ4TxOwP9HmXXmb_w-lNQwutreYihAb51sgx8LQdFAhIEEou1w?key=ICzLerXjukSgelnUIdp7Y9vf)

  

# 13). Start the Grafana Container

*   Launch Grafana using the following command:
    

| podman run -d --name=grafana -p 3000:3000 docker.io/grafana/grafana:latest |
| --- |

*   podman run: Starts a new container based on the specified image.
    
*   \-d: Runs the container in detached mode (background).
    
*   \--name=grafana: Assigns the name grafana to the container for easier management and identification.
    
*   \-p 3000:3000: Maps port 3000 on the host to port 3000 in the container.
    
*   Grafana's web interface is accessible on http://<host-IP>:3000.
    
*   [docker.io/grafana/grafana:latest](http://docker.io/grafana/grafana:latest): Specifies the Grafana image from Docker Hub (grafana/grafana) and uses the latest version tag.
    

  
  

*   Verify Grafana is running:
    

| $ podman ps |
| --- |

  

# 14). Access Grafana

*   Open your web browser and go to:
    

| http://localhost:3000 |
| --- |

  

*   Log in using the default credentials:
    

1.  Username: admin
    
2.  Password: admin
    

*   Change the default password when prompted.
    

Figure 12: Access Grafana

![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXdfRrFhEDFZaYnrRRyG0Y_dFAZyETXNoN9hMss2yn27fEwD1ECfWtuTSPFrBktnUAGTCEzBF-EXT8FhLNhBfJHLfYFHzKU3yVOlWZAGQpD-KEzvSY3sbYUHV0oflFvzqDYdY_O2Dg?key=ICzLerXjukSgelnUIdp7Y9vf)

  
  

# 15). Add Data Source in Grafana

*   In Grafana, navigate to Configuration > Data Sources.
    
*   Click Add data source and select Prometheus from the list.
    
*   Configure the Prometheus data source:
    

*   URL: [http://localhost:9090](http://localhost:9090)
    
*   URL: http://<IP>:9090 \[ For different network\]
    

*   Click Save & Test to verify the connection.
    

  
  

Figure 15\[A\]: Add Data Source in Grafana

![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXeywMt4vvwGhSgsmJ6mUmp3G3GtcARq_3mxKLBfa51SFVlLotrOi17usLEiTyl4XTVMOnwkyJPKkWCZn1M-yB9mFEgJy594ytIoUHh5rJ8hyMuBQJJkBTtHW3GTNNVm9soNsSuZ?key=ICzLerXjukSgelnUIdp7Y9vf)

Figure 15\[B\]: Configure datasource in grafana

![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXd_HbdvoNfxyT83RdtCU49BBsZiRfcMQfTzlS0j4zb2nPB5kThyNHXn-mS7-nM4qPnPVJyN292m9sSRLO3wGW1Z6-L9Gy9DsZIKSkv4OFQ-oh4XZa758RgHyjZbThNoWi1wnATt6Q?key=ICzLerXjukSgelnUIdp7Y9vf)

  
  
  
  
  
  
  
  

# 16). Create and Import a Dashboard in Grafana

*   Go to the Grafana home page and click \+ > Import.
    
*   Enter a dashboard ID or upload a JSON file for a pre-configured Keycloak metrics dashboard.
    
*   Select the Prometheus data source.
    
*   Click Import to load the dashboard.
    

Figure 16\[A\]: Create and Import a Dashboard in Grafana

![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXeL3MbHP-V96u5zlwoqQUC9OLjyvNvSqod9juJIz1GE_sHtK7bj6ICfgAzObDspxGLEN7ienukN2ul1tBe3eobS2A76U94QcuP_XedOy7aiTPcx9946j44yay69C27qgioYi267IQ?key=ICzLerXjukSgelnUIdp7Y9vf)

Figure 16\[B\]: Import dashboard or find dashboard by Clipboard ID

![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXcaT6NR1f5Vxw2wXs6CWbajIEp4JkfsRh8Qm0oyoZxNHhcO81m8U2kbf9JpaUE_G048dbpPz4dIG2bjyDlqyLmbjFyXZ7ChwkBGlLQ_xOeHH8JnGOwdJ-ltJqZZVLIlDJb0qTKYWA?key=ICzLerXjukSgelnUIdp7Y9vf)

  
  
  
  
  
  
  
  
  

Setting up 389 Directory Server (LDAP) and Integrating with Keycloak

This Section details the steps to set up a 389 Directory Server (LDAP), create user entries, and integrate it with Keycloak for user federation. It enables centralized user authentication and management via Keycloak.

  

# 17). Deploying the Ldap389 Directory Server

*   Run the Ldap389 Directory Server container:
    

| podman run -d --name ldap_KNA -e DS_DM_PASSWORD=redhat -p 3390:3389 docker.io/389ds/dirsrv:latest |
| --- |

*   podman run: Starts a new container based on the specified image.
    
*   \-d: Runs the container in detached mode (background).
    
*   \--name ldap\_KNA: Assigns the name ldap\_KNA to the container for easier identification.
    
*   \-e DS\_DM\_PASSWORD=redhat: Sets the environment variable DS\_DM\_PASSWORD to redhat.
    
*   This specifies the Directory Manager's password for the LDAP server.
    
*   \-p 3390:3389: Maps port 3390 on the host to port 3389 in the container.
    
*   This makes the LDAP server accessible on the host machine via port 3390.
    
*   [docker.io/389ds/dirsrv:latest](http://docker.io/389ds/dirsrv:latest): Specifies the image for 389 Directory Server (389ds/dirsrv) and uses the latest version tag.
    

  
  
  
  
  

# 18). Accessing the LDAP Container

*   Run an interactive bash session in the LDAP container:
    

| $ podman exec -it ldap_KNA bash |
| --- |

  
  
  

# 19). Configuring the Directory Backend

*   Create a new database backend:
    

| $ dsconf localhost backend create --be-name exampleDB --suffix dc=example,dc=com |
| --- |

  

# 20). Defining the LDAP Directory Structure

*   Create a file named base.ldif to define the domain and an organizational unit for users:
    

| $ vim base.ldif |
| --- |

  

*   Add the following content:
    

| dn: dc=example,dc=comobjectClass: topobjectClass: domaindn: ou=users,dc=example,dc=comobjectClass: organizationalUnitou: users |
| --- |

  
  

*   Add the entries to the LDAP directory:
    

| $ ldapadd -H ldap://localhost:3389 -D "cn=Directory Manager" -w redhat -f base.ldif |
| --- |

  

# 21). Adding User Entries

*   Create a file named users.ldif to define user entries:
    

| $ vim users.ldif |
| --- |

  

*   Add the following content:
    

| dn: uid=user1,ou=users,dc=example,dc=comobjectClass: inetOrgPersonuid: user1sn: User1givenName: User1cn: User OnedisplayName: User OneuserPassword: manish123mail: user1@example.comdn: uid=user2,ou=users,dc=example,dc=comobjectClass: inetOrgPersonuid: user2sn: User2givenName: User2cn: User TwodisplayName: User TwouserPassword: manish123mail: user2@example.com |
| --- |

  
  

*   Add the users to the LDAP directory:
    

| $ ldapadd -H ldap://localhost:3389 -D "cn=Directory Manager" -w redhat -f users.ldif |
| --- |

  

# 22). Verifying LDAP Entries

*   Run an LDAP search to verify the users have been added:
    

| $ ldapsearch -x -H ldap://localhost:3389 -D "cn=Directory Manager" -w redhat -b "dc=example,dc=com" "(objectClass=inetOrgPerson)" |
| --- |

  

# 23). Configuring User Federation in Keycloak

## 23.1: Access the Keycloak Admin Console:       

*   Navigate to the Keycloak admin console in your browser ( http://localhost:8080/admin).
    

  

Figure 23.1: Access the Keycloak Admin Console:  

![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXcmOTzivBL5W97HYuB3Ax7_T7ITqRFDPgtcB8Wdo1dRSnqLoAJQ0XdK0xAGKYXhiP5Kru9whEDakXwlB5bTDQJklUZrl_US756qVlVkzpBGdNL8-EhHUtxMI099w8rJIWtcjJbU0A?key=ICzLerXjukSgelnUIdp7Y9vf)

  

## 23.2: Enable LDAP Federation:

*   Go to User Federation in the left-hand menu.
    
*   Select Add Provider and choose LDAP.
    

Figure 23.2: Enable LDAP Federation

![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXdAC7e_Mfh1jnstUijbRyi6-qa3YoHzKu4UFer39VUAMgHmivfyP-V5J0jjDUhPfCge-3ZjGYkPmXbYjF_VPwb_RhTokjg9Eetg3g6Rk5EgPd-GetWYCzrSRn_AXTq-KPj1yS8Obw?key=ICzLerXjukSgelnUIdp7Y9vf)

##     23.3:  Configure LDAP Provider:

*   Set the following values:
    

*   Connection URL: ldap://ldap\_KNA:3389
    
*   Bind DN: cn=Directory Manager
    
*   Bind Credential: redhat
    
*   Users DN: ou=users,dc=example,dc=com
    
*   Search Scope: Subtree.
    
*   Sync Settings: Enable periodic synchronization if needed.
    

*   Click Save.
    

Figure 23.3\[A\]: Configure LDAP Provider

![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXcP-bxKODTj28B_yyAbrcFgGGcPKXKQYqsf24IHcpHbpHhC6y1HUx009Qwgs7o46nUZwyVeyQn8BFHDO2ABUd9Q9VVwskcl_QHHFuNxKWhL2Sz0VzbgLf6WLFmX0w-pL-82jjYgUA?key=ICzLerXjukSgelnUIdp7Y9vf)

Figure 23.3\[B\]: Configure LDAP Provider

![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXdSi3e8CQUxkdCzVm6jTwzAKIzHpb0P9xde8oS_MtazSglMILCZ0kzVIHUWhLZTm7HGztOoF3xJAqqC3hRisuoYPq-oIE3DSI35OQa2RWNBuqswr17JN9mgBgJAtVt5_VaqjsCG-g?key=ICzLerXjukSgelnUIdp7Y9vf)

  
  
  
  
  
  
  
  

Figure 23.3\[C\]: Configure LDAP Provider

![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXeAB28tF_RNP7SehBjzW5b0aTU0NRiQEhOsrKD1HWaSVOZJYfQbsRA7OWY7PAqsw-evR4q2lum2w1KLsXPOddAABpqqPVN66luGXQneyTN4hT0mnEcY2ECpR1uhr7SLVf74CeL4KA?key=ICzLerXjukSgelnUIdp7Y9vf)

##           23.4: Synchronize Users:

*   After saving, click on the Sync All Users button to import LDAP users into Keycloak.
    

# 24).  User Login with LDAP in Keycloak

*   Navigate to the Keycloak login page.
    
*   Enter the credentials for an LDAP user (e.g., user1 with password \*\*\*\*\*\*\*\*\*).
    
*   Successful login confirms that the LDAP user federation is functioning correctly.
    

Figure 24\[A\]: Get url for users login from client section

![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXdHHEOqy1OvqigKE3Gv3DSxFocwAMwNvMNFadUB3uXpyNNqSS85AenRf2fbqn4qvas38ADB_8cKrXkbQN6lqwcopQPeqh9qR05C5hCJMcp6EYEfFVqzDw8Tuv4avxHQETQC3rVYHg?key=ICzLerXjukSgelnUIdp7Y9vf)

Figure 24\[B\]: Check users personal information after login

![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXd4h-XPcpsyrcc7MtMCiAbEjPn-bbyk9t-36zYmnHIzmjL3MgChzOpfsG_PK6uzJxWtSZyAyM21l-58QJQ2li37UgYXrNO2Kyr7udCRJDMzw84huEYr9Vtc10v6b-rGLstrv0S3fg?key=ICzLerXjukSgelnUIdp7Y9vf)
