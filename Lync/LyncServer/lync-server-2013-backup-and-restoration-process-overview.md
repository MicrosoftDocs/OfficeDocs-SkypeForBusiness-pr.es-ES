---
title: Información general del proceso de copia de seguridad y restauración
TOCTitle: Información general del proceso de copia de seguridad y restauración
ms:assetid: e0f23b21-070f-4df5-b795-cea2f5338d85
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Hh202192(v=OCS.15)
ms:contentKeyID: 52061848
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Información general del proceso de copia de seguridad y restauración

 

_**Última modificación del tema:** 2013-03-26_

En esta sección se proporciona información general sobre cómo funciona el proceso de copia de seguridad y restauración en Lync Server 2013. El proceso para todos los servidores Standard Edition y Enterprise es el mismo, independientemente de su ubicación.

En general, el proceso de copia de seguridad funciona de la siguiente forma:

  - Se crea una ubicación para copias de seguridad como una carpeta compartida en un equipo independiente que no forma parte de ningún grupo de servidores. La ubicación de la copia de seguridad refiere a **$Backup**.

  - De manera periódica y programada, se hace una copia de seguridad de todas las bases de datos de Lync Server y de todos los almacenes de archivos que se describen en [Requisitos de copia de seguridad y restauración: datos](lync-server-2013-backup-and-restoration-requirements-data.md) siguiendo los procedimientos de [Copia de seguridad de Lync Server](lync-server-2013-backing-up-lync-server.md). El Almacén de administración central incluye todos los parámetros y configuraciones de servidor.

  - Cada vez que se ejecuta una copia de seguridad posterior, se crea una nueva carpeta compartida y cambia la ruta a la que hace referencia **$Backup**.

En general, el proceso de restauración funciona de la siguiente forma:

  - Cuando se produce un error o interrupción del servicio, se restauran los datos en la ubicación a la que hace referencia **$Backup** en equipos nuevos o limpios.
    
    > [!IMPORTANT]  
    > Este proceso de restauración no restaura datos en un estado de servidor existente. Es decir, este proceso requiere que el servidor esté limpio o sea nuevo.
    


  - Para hacer que la información de usuarios y conferencias se pueda recuperar en el punto de error, se puede implementar una topología de recuperación ante desastres con grupos de servidores front-end emparejados, tal y como se describe en [Planeación de alta disponibilidad y recuperación ante desastres en Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md). Aparte de esta opción, Lync Server admite únicamente el modelo de recuperación simple para las bases de datos. Con este modelo, las bases de datos se recuperan en el punto donde se realizó la última copia de seguridad completa, por lo que una base de datos no se podrá restaurar en el punto de error o en un punto específico en el tiempo. En muchas organizaciones, el modelo de recuperación simple es el mejor, ya que la base de datos back-end de Lync Server (RTCXDS.mdf) es en realidad más pequeña que los archivos de registro transaccionales y notablemente más pequeña que las de las típicas aplicaciones de base de datos de línea de negocio.

  - Toda la configuración del Sistema de nombres de dominio (DNS), del Protocolo de la configuración dinámica de host (DHCP), los nombres de dominio, los nombres de dominio completos (FQDN), las rutas de almacenes de archivos, etc. deben ser los mismos al momento de la restauración que cuando se hizo la copia de seguridad.

Si se produce un error en un servidor que ejecuta Lync Server, la recuperación incluye los siguientes pasos:

  - Instalar el sistema operativo en un equipo nuevo o limpio con el mismo FQDN que había en el equipo donde se produjo el error.

  - Reinstalar certificados.

  - Si el servidor hospedaba una base de datos, instale Microsoft SQL Server 2012 o Microsoft SQL Server 2008 R2.

  - En general, si el servidor hospedaba una base de datos, ejecute Generador de topologías para crear e instalar la base de datos y establecer listas de control de acceso (ACL).

  - En general, si el servidor hospedaba un rol de servidor, realice los pasos del 1 al 4 del Asistente para la implementación de Lync Server para instalar los archivos de configuración locales, instalar los componentes de rol de servidor, asignar certificados e iniciar los servicios.
    

    > [!NOTE]
    > Si el servidor hospedaba una base de datos combinada con un rol de servidor, siga el paso 2 del Asistente para la implementación de Lync Server para volver a crear la base de datos.



  - Si el servidor hospedaba una base de datos, restaure los datos de la copia de seguridad.

