---
title: 'Lync Server 2013: Reforzar y proteger las bases de datos'
TOCTitle: Reforzar y proteger las bases de datos de Lync Server 2013
ms:assetid: 6953e721-3511-4235-b848-51bab093dc89
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Dn518330(v=OCS.15)
ms:contentKeyID: 60505975
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Reforzar y proteger las bases de datos de Lync Server 2013

 

_**Última modificación del tema:** 2016-12-08_

Microsoft Lync Server 2013 también depende de las bases de datos de SQL Server para almacenar la información del usuario, el estado de conferencias, archivar datos y los registros detallados de llamadas (CDR). Puede maximizar la disponibilidad de los datos de Lync Server 2013 en las bases de datos back-end de Lync Server si divide en particiones los datos de manera que mejore la tolerancia a errores y simplifique la resolución de problemas. Para lograr estos objetivos, divida en particiones los datos de la aplicación haciendo lo siguiente:

  - **Aplicar las prácticas recomendadas para crear particiones de servidor** Separe los datos del sistema operativo, de aplicaciones y programas de los archivos de datos.

  - **Almacenar archivos de registros de transacciones y archivos de base de datos** Almacene estos archivos por separado para aumentar la tolerancia a errores y optimizar la recuperación, y almacénelos en un disco o volumen cifrado.

  - **Usar clústeres de servidores**: coloque en clústeres los servidores back-end para optimizar la disponibilidad del sistema de Lync Server 2013.

  - **Asegúrese de que todas las copias de seguridad estén cifradas y administradas correctamente:** los medios perdidos, descartados o almacenados en una ubicación incorrecta pueden representar una amenaza importante para la seguridad de los datos que hay en las implementaciones de Lync Server 2013.

No se puede acceder de forma remota a la instancia de SQL Server Express (instancia RTCLOCAL) en ningún servidor de Lync Server 2013, excepto en el servidor Standard Edition; y tampoco se crean excepciones de firewall local, salvo para SQL Server Express en un servidor Standard Edition. En un servidor Standard Edition, tanto la base de datos back-end como el Almacén de administración central (CMS) están configurados para poder acceder a ellos de forma remota. Para proteger las bases de datos de SQL Server, puede hacer lo siguiente:

  - Personalizar el firewall de SQL Server Express en los servidores Standard Edition, limitando el ámbito de servidores que pueden acceder de forma remota a la base de datos. De manera predeterminada, cualquier dirección IP puede acceder a la base de datos de forma remota.

  - Usar el Administrador de configuración de SQL Server para especificar los protocolos, direcciones IP y puertos para el acceso remoto a SQL Server:
    
      - Lync Server 2013 usa el protocolo TCP/IP. Admite la versión 4 de IP (IPv4), pero no admite la versión 6 (IPv6).
        

        > [!NOTE]
        > Lync Server 2013 puede funcionar en una red con una pila de IP dual habilitada.

    
      - Lync Server 2013 admite varias direcciones IP (tarjetas de direcciones de red en múltiples ubicaciones). Puede especificar que SQL Server escuche solo direcciones IP específicas (direcciones individuales o por subred) y use solo protocolos específicos.
    
      - Lync Server 2013 admite puertos de SQL Server estáticos y dinámicos.

  - Ejecute SQL Server en un puerto estático (que no sea predeterminado) y no ejecute SQL Server Browser (para que no pueda informar del puerto de escucha al cliente). Para esto, es necesario tener una configuración personalizada en cada cliente de SQL Server, lo cual incluye servidores front-end, servidor de supervisión, servidor de archivado y consolas administrativas (que ejecuten Shell de administración de Lync Server, Panel de control de Lync Server o Generador de topologías), y otros servidores que ejecuten bases de datos de Lync Server).


> [!NOTE]
> El acceso a las bases de datos debe limitarse a los administradores de bases de datos de confianza. Un administrador de base de datos malintencionado podría insertar o modificar datos en las bases de datos para obtener privilegios sobre los servidores de Lync Server 2013 u obtener información confidencial de los servicios, aunque no se le haya otorgado acceso directo o control de los servidores de Lync Server 2013 al administrador de la base de datos.



Si quiere detalles sobre configuraciones personalizadas y cómo reforzar las bases de datos de SQL Server, vea el artículo del blog "Usar Lync Server 2010 con una configuración de red personalizada de SQL Server," en [http://go.microsoft.com/fwlink/p/?LinkId=214008](http://go.microsoft.com/fwlink/p/?linkid=214008).


> [!NOTE]
> También puede proteger los sistemas operativos y los servidores de aplicaciones y puede utilizar directivas de grupo para aplicar bloqueos de seguridad en la implementación de Lync Server. Para obtener información detallada, consulte <A href="lync-server-2013-hardening-and-protecting-servers-and-applications.md">Reforzar y proteger los servidores y las aplicaciones de Lync Server 2013</A>.


