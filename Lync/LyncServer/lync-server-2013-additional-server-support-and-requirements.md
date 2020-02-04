---
title: 'Lync Server 2013: Compatibilidad y requisitos para un servidor adicional'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Additional server support and requirements
ms:assetid: 7622986b-abd6-4f45-8b5b-d5e2368521e8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398577(v=OCS.15)
ms:contentKeyID: 48184535
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3f111b80bc88b632ff1020f45e899f220edeb7d5
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41738019"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="additional-server-support-and-requirements-in-lync-server-2013"></a>Compatibilidad y requisitos para un servidor adicional en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-12-09_

Además de la compatibilidad de software que se describe en las otras secciones de esta documentación de compatibilidad, Lync Server 2013 tiene las siguientes limitaciones de compatibilidad:

  - Lync Server 2013 admite el sistema de nombres de dominio (DNS) y el equilibrio de carga de hardware para roles de servidor específicos. También admite el equilibrio de carga de la aplicación para servidores de mediación, cuando corresponda. Para obtener información sobre Cuándo usar cada uno, consulte la documentación de planificación.

  - Lync Server 2013 usa el protocolo de expansión de lista de distribución (DLX) para expandir las listas de distribución. Este protocolo especifica también el método de servicio Web que se usa para obtener la pertenencia a una lista de distribución. Microsoft Exchange Server admite grupos dinámicos que no tienen miembros asignados de forma estática. En su lugar, almacenan consultas que se evalúan cuando se expande el grupo. DLX no admite listas de distribución dinámicas. Esta limitación de DLX se aplica a todas las versiones de Lync Server.

  - El Asistente para habilitar usuarios no admite la conversión automática de caracteres no ingleses a un URI compatible con SIP, por lo que debe modificar la dirección SIP de forma manual.

  - Para los servidores que ejecutan software antivirus, consulte [exclusiones de detección antivirus para Lync Server 2013](lync-server-2013-antivirus-scanning-exclusions.md) para conocer sugerencias de exclusiones de virus y otras recomendaciones relacionadas con la seguridad.

  - Si usa IPsec, se recomienda deshabilitar IPsec en los intervalos de puertos que se usan para el tráfico de audio y vídeo. Para obtener más información, consulte [excepciones de IPSec en Lync Server 2013](lync-server-2013-ipsec-exceptions.md) en la documentación de planeación.

  - Si la organización usa una infraestructura QoS (Calidad de servicio), el subsistema de medios estará diseñado de modo que funcione con esta infraestructura existente. Para obtener más información sobre cómo implementar QoS, consulte [Administración de calidad de servicio (QoS) en Lync Server 2013](lync-server-2013-managing-quality-of-service-qos.md) en la documentación de operaciones.

  - Se admite el uso del firewall del sistema operativo. Lync Server 2013 administra las excepciones de Firewall para el firewall del sistema operativo, excepto el software de base de datos de Microsoft SQL Server. Para obtener más información sobre los requisitos de Firewall de SQL Server, consulte la documentación de SQL Server.

  - Las interfaces externas usadas para implementar la compatibilidad con el acceso de usuarios externos deben estar en una subred independiente, *no* en la misma red que las interfaces internas.

  - La capacidad XMPP de Lync Server 2013 está probada y es compatible con Microsoft para la federación de mensajería instantánea con Google Talk. Para otros sistemas XMPP, póngase en contacto con el proveedor para comprobar que son compatibles con la federación con Lync Server 2013 y para cualquier recomendación sobre implementación o solución de problemas.

  - Con el lanzamiento de las actualizaciones acumulativas de Lync Server 2013:2013 de julio, Lync Server 2013 ahora es compatible con la autenticación en dos fases. Para obtener más información, vea [autenticación en dos fases en Lync Server 2013](lync-server-2013-planning-for-and-deploying-two-factor-authentication.md).

  - La mayoría de los servidores internos requieren un tipo de certificado definido como **autenticación abierta** (OAuth). Debe solicitar y asignar un certificado de OAuth durante la **solicitud, instalar y asignar certificados,** fase del Asistente para la implementación de Lync Server. El tamaño mínimo de una clave de certificado de OAuth es de 1024 bits. Puede aparecer una advertencia si solicita un certificado con una longitud de clave inferior a 2048 bits de longitud. Para evitar posibles problemas en caso de que se aplique una longitud de clave de 2048 en lugar de advertencias, se recomienda encarecidamente usar siempre una longitud de clave de 2048 para los certificados de OAuth.

  - Lync Server 2013 y Microsoft Exchange Server 2010 Service Pack 1 (SP1) funcionan con compatibilidad con los algoritmos estándar federal de procesamiento de información (FIPS) 140-2 si los sistemas operativos Windows Server 2008 R2 están configurados para usar los algoritmos FIPS 140-2 para criptografía del sistema. Para implementar la compatibilidad con FIPS, debe configurar cada servidor que ejecute Lync Server 2013 de soporte técnico. Para obtener detalles sobre los algoritmos compatibles con FIPS y cómo implementar la compatibilidad con FIPS, consulte el artículo 811833 de Microsoft Knowledge base, "criptografía de sistema: usar algoritmos compatibles con FIPS para cifrado, hash y configuración de seguridad de firma en Windows XP [http://go.microsoft.com/fwlink/p/?linkid=3052\&kbid=811833](http://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=811833)y en versiones posteriores de Windows en. Para obtener más información sobre las limitaciones y la compatibilidad de FIPS 140-2 en Exchange 2010, consulte "Exchange 2010 SP1 y la compatibilidad con [http://go.microsoft.com/fwlink/p/?linkId=205335](http://go.microsoft.com/fwlink/p/?linkid=205335)los algoritmos compatibles con FIPS" en.

Lync Server 2013 requiere la instalación de otro software en componentes específicos antes o durante la implementación. Esto incluye el software que está disponible con el sistema operativo, el software descargable y el software que se instala automáticamente durante la instalación de Lync Server 2013. A continuación se muestra una lista de software adicional que puede ser necesario:

  - Windows Update

  - Windows Identity Foundation

  - Microsoft .NET Framework 4,5

  - Redistribuible de Microsoft Visual C++ 2012
    
    <div>
    

    > [!NOTE]  
    > Microsoft Visual C++ redistribuible 2012 se instala automáticamente al instalar Lync Server 2013. No debe instalar ni utilizar ninguna otra versión.

    
    </div>

  - Módulo dirección URL redistribuida versión 2,0 redistribuible

  - Motor en tiempo de ejecución de Windows Media Format

  - Windows PowerShell versión 3,0

  - Complemento del explorador de Microsoft Silverlight 4 (Silverlight 4.0.50524.0 o la versión más reciente del panel de control de Lync Server)

  - Herramientas de servicios de dominio de Active Directory

Algunos de estos requisitos de software solo se aplican a roles o componentes de servidor específicos. Para obtener más información sobre estos requisitos de software, consulte [requisitos de software adicionales para Lync Server 2013](lync-server-2013-additional-software-requirements.md) en la documentación de planeación.

</div>

<span> </span>

</div>

</div>

</div>

