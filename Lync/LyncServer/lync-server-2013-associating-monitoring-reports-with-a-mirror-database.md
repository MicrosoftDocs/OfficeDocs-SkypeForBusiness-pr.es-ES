---
title: Asociación de informes de supervisión con una base de datos reflejada
TOCTitle: Asociación de informes de supervisión con una base de datos reflejada
ms:assetid: 42b797c6-8db8-4ad7-886e-8ddf8deb06f9
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ945624(v=OCS.15)
ms:contentKeyID: 52061671
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Asociación de informes de supervisión con una base de datos reflejada

 

_**Última modificación del tema:** 2014-02-07_

Si configura una base de datos reflejada para supervisar su base de datos, la reflejada asumirá el puesto de la base de datos principal cuando se produzca una conmutación por error. Sin embargo, si utiliza los informes de supervisión de Lync Server y se produce una conmutación por error, podría observar que los informes de supervisión no corresponden a la base de datos reflejada. Esto se debe a que, al instalar los informes de supervisión, solo se ha especificado la ubicación de la base de datos principal y no la de la base de datos reflejada.

Para que los informes de supervisión pasen automáticamente a la base datos reflejada en caso de conmutación por error, debe agregar la base de datos reflejada como "socio de conmutación por error" a las dos bases de datos que utilizan informes de supervisión (una base datos para los datos del Registro de detalles de llamadas y otra para los datos de Calidad de la experiencia). (Tenga presente que este paso se ha de realizar después de haber instalado los informes de supervisión.) Puede agregar información de socio de conmutación por error manualmente editando los valores de la cadena de conexión que utilizan las dos bases de datos. Para ello, realice el procedimiento siguiente:

1.  Use Internet Explorer para abrir la página de inicio de **SQL Server Reporting Services**. La dirección URL de la página de inicio de Reporting Services está formada por:
    
      - El prefijo **http:**.
    
      - El nombre de dominio completo (FQDN) del equipo en el que se ha instalado Reporting Services (por ejemplo, **atl-sql-001.litwareinc.com**).
    
      - La cadena de caracteres **/Reports\_**.
    
      - El nombre de la instancia de la base de datos en la que están instalados los informes de supervisión (por ejemplo, **archinst**).
    
    Por ejemplo, si se ha instalado SQL Server Reporting Services en el equipo atl-sql-001.litwareinc.com y los informes de supervisión utilizan la instancia de base de datos archinst, la dirección URL de la página de inicio será:
    
    **http://atl-sql-001.litwareinc.com/Reports\_archinst**

2.  Cuando haya accedido a la página de inicio de Reporting Services, haga clic en **LyncServerReports** y en **Reports\_Content**. De este modo accederá a la página **Reports\_Content** de los informes de supervisión de Lync Server.

3.  En la página **Reports\_Content**, haga clic en el origen de datos **CDRDB**.

4.  En la página **CDRDB**, en la ficha **Propiedades**, busque el cuadro de texto titulado **Cadena de conexión**. La cadena de conexión actual será similar a:
    
    **Data source=(local)\\archinst;initial catalog=LcsCDR**

5.  Modifique la cadena de conexión para incluir el nombre del servidor y la instancia de base de datos de la base de datos reflejada. Por ejemplo, si el servidor se llama atl-mirror-001 y la base de datos reflejada se encuentra en la instancia archinst, tendrá que agregar para especificar la base de datos reflejada esta sintaxis:
    
    **Failover Partner=atl-mirror-001\\archinst**
    
    La cadena de conexión resultante deberá ser:
    
    **Data source=(local)\\archinst;Failover Partner=atl-mirror-001\\archinst;initial catalog=LcsCDR**

6.  Cuando haya actualizado la cadena de conexión, haga clic en **Aplicar**.

7.  En la página **CDRDB**, haga clic en el vínculo **Reports\_Content**. Haga clic en el origen de datos **QMSDB** y, a continuación, modifique la cadena de conexión de la base de datos QoE. Por ejemplo:
    
    **Data source=(local)\\archinst;Failover Partner=atl-mirror-001\\archinst;initial catalog=QoEMetrics**

8.  Haga clic en **Aplicar**.

## Vea también

#### Conceptos

[Instalación de informes de supervisión de Lync Server 2013](lync-server-2013-installing-lync-server-2013-monitoring-reports.md)  
[Usar informes de supervisión en Lync Server 2013](lync-server-2013-using-monitoring-reports.md)

