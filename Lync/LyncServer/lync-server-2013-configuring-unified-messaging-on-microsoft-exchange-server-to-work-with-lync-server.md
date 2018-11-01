---
title: "Configuración de mensajería unificada en MS Exchange Server con Lync Server 2013"
TOCTitle: Configuración de la mensajería unificada en Microsoft Exchange Server para trabajar con Lync Server 2013
ms:assetid: 058da9c4-23af-4ddb-9f63-70133a8aafc6
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg398106(v=OCS.15)
ms:contentKeyID: 48274301
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuración de la mensajería unificada en Microsoft Exchange Server para trabajar con Lync Server 2013

 

_**Última modificación del tema:** 2016-12-08_

> [!IMPORTANT]  
> Si desea usar Mensajería unificada de Exchange (UM) para proporcionar a los usuarios de Telefonía IP empresarial contestador automático, Outlook Voice Access o servicios de operador automático, lea <a href="lync-server-2013-planning-for-exchange-unified-messaging-integration.md">Planear la integración de la mensajería unificada de Exchange en Lync Server 2013</a> en la documentación referente a la planeación y siga las instrucciones de esta sección.



Para configurar Mensajería unificada de Exchange (UM) para que trabaje con Telefonía IP empresarial, tendrá que llevar a cabo las siguientes tareas:

  - Configurar certificados en el servidor que ejecuta los servicios de Mensajería unificada de Exchange (UM)
    

    > [!NOTE]
    > Agregue todos los servidores de buzón de correo y de acceso de cliente a todos los planes de marcado URI de SIP de mensajería unificada. De no hacerlo así, el enrutamiento de llamadas salientes no funcionará de la manera prevista.



  - Cree uno o varios planes de marcado del URI de SIP de mensajería unificada, junto con los números de teléfono de acceso de suscriptor, si fuera necesario, y, posteriormente, cree los planes de marcado de Lync Server correspondientes.

  - Use el script **exchucutil.ps1** para:
    
      - Crear puertas de enlace IP de Mensajería unificada.
    
      - Crear grupos de extensiones de Mensajería unificada.
    
      - Garantizar que Lync Server 2013 tiene permiso para leer objetos de Servicios de dominio de Active Directory de Mensajería unificada.

  - Cree un objeto operador automático de Mensajería unificada.

  - Cree un objeto de acceso de suscriptor.

  - Cree un URI de SIP para cada usuario y asociar usuarios a un plan de marcado del URI de SIP de Mensajería unificada.

## Requisitos y recomendaciones

En la documentación de esta sección se asume que ha implementado los siguientes roles de Exchange 2013: acceso de cliente y buzón de correo. En Microsoft Exchange Server 2013, Mensajería unificada de Exchange se ejecuta como un servicio en estos servidores.

Para obtener más información acerca de la implementación de Exchange 2013, vea la biblioteca de Technet referente a Exchange 2013 en [http://go.microsoft.com/fwlink/?linkid=266637\&clcid=0xC0A](http://go.microsoft.com/fwlink/?linkid=266637%26clcid=0xc0a).

También debe tener en cuenta lo siguiente:

  - Si se instala Mensajería unificada de Exchange en varios bosques, los pasos de la integración de Exchange Server se deben realizar para cada uno de los bosques de Mensajería unificada. Además, cada bosque de Mensajería unificada se debe configurar para que confíe en el bosque en el que se implementa Lync Server 2013, y el bosque en el que se implementa Lync Server 2013 se debe configurar para que confíe en cada uno de los bosques de Mensajería unificada.

  - Los pasos de la integración se realizan en los roles de Exchange Server donde se ejecutan los servicios de Mensajería unificada y en el servidor que ejecuta Lync Server 2013. Los pasos de integración de la Mensajería unificada de Exchange Server deben realizarse antes que los pasos de integración de Lync Server 2013.
    

    > [!NOTE]
    > Para consultar qué pasos de integración se realizan en qué servidores y mediante qué roles de administrador, consulte <A href="lync-server-2013-deployment-process-for-integrating-on-premises-unified-messaging.md">Proceso de implementación de la integración de la mensajería unificada local y Lync Server 2013</A>.



Las herramientas siguientes deben estar disponibles en cada uno de los servidores que ejecuten Mensajería unificada de Exchange:

  - Shell de administración de Exchange

  - El script **exchucutil.ps1**, que realiza las siguientes tareas:
    
      - Crea una puerta de enlace IP de Mensajería unificada para cada Lync Server 2013.
    
      - Crea un grupo de búsqueda para cada puerta de enlace. El identificador piloto de cada grupo de búsqueda especifica el plan de marcado del URI de SIP de mensajería unificada utilizado por el Grupo de servidores front-end o Servidor Standard Edition asociado a la puerta de enlace.
    
      - Garantiza el permiso de Lync Server 2013 para leer objetos de Mensajería unificada de Exchange en Servicios de dominio de Active Directory.

## En esta sección

  - [Configurar certificados en el servidor que ejecuta la mensajería unificada de Microsoft Exchange Server](lync-server-2013-configure-certificates-on-the-server-running-microsoft-exchange-server-unified-messaging.md)

  - [Configuración de la mensajería unificada de Microsoft Exchange en Lync Server 2013](lync-server-2013-configure-unified-messaging-on-microsoft-exchange.md)

