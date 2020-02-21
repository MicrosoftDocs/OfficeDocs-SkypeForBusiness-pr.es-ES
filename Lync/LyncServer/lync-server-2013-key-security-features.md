---
title: 'Lync Server 2013: características de seguridad clave'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Key security features in Lync Server 2013
ms:assetid: bf2a3b8f-73c6-47e1-8c9e-ca1dc1a502bf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn342829(v=OCS.15)
ms:contentKeyID: 56107266
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 20205bb401132143b0bcda28343e4ae3bcfd93b2
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42186783"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="key-security-features-in-lync-server-2013"></a>Características de seguridad clave en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-07-18_

Lync Server 2013 incluye varias características de seguridad, como la autenticación de servidor a servidor, el control de acceso basado en roles y el almacenamiento centralizado de los datos de configuración.

En este artículo se proporciona información general de alto nivel sobre la seguridad de Lync Server 2013.

<div>

## <a name="key-security-features-in-lync-server-2013"></a>Características de seguridad clave en Lync Server 2013

La seguridad es un tema muy amplio. La seguridad alcanza todas las características de Lync Server 2013, así como las bases de datos, los servicios y el hardware que constituyen un ecosistema de Lync. En este artículo se describen algunas de las características de Lync Server 2013 en particular diseñadas para la seguridad.

<div>

## <a name="planning-and-design-tools"></a>Herramientas de planeación y diseño

Lync Server 2013 ofrece dos herramientas para facilitar la planeación y el diseño, y para reducir la posibilidad de configurar de forma indebido los componentes de Lync Server.

  - La **herramienta de planeación** de la topología automatiza gran parte del proceso de diseño de la topología. Puede exportar los resultados de la herramienta de planeación al generador de topologías, que es la herramienta necesaria para instalar cada servidor que ejecuta Lync Server 2013.

  - El **generador de topologías** almacena toda la información de configuración en el almacén de administración central.

Para obtener más información sobre estas herramientas, consulte [Planning for Lync Server 2013](lync-server-2013-planning.md).

</div>

<div>

## <a name="central-management-store"></a>Almacén de administración central

En Lync Server 2013, los datos de configuración de los servidores y los servicios forman parte del almacén de administración central. El almacén de administración central proporciona un almacenamiento sólido y esquematizado de los datos necesarios para definir, configurar, mantener, administrar, describir y usar una implementación de Lync Server. También valida los datos para garantizar la coherencia de la configuración. Todos los cambios en estos datos de configuración ocurren en el almacén de administración central, lo que elimina los problemas de "falta de sincronización".

Las copias de solo lectura de los datos se replican a todos los servidores de la topología, incluidos los servidores perimetrales. La replicación se administra por medio de un servicio que, de manera predeterminada, se ejecuta en el contexto del servicio de red limitando los derechos y permisos a los de un simple usuario del equipo.

</div>

<div>

## <a name="server-to-server-authentication"></a>Autenticación de servidor a servidor

En Lync Server 2013, la autenticación se puede configurar entre servidores mediante el protocolo Open Authorization (OAuth). Por ejemplo, puede configurar Lync Server 2013 para autenticarse con un servidor que ejecute Exchange Server 2013. Con el protocolo OAuth, el servidor Lync y el servidor Exchange pueden confiar entre sí. Esto proporciona la capacidad de integrar los productos de manera transparente. Para obtener más información, consulte [Managing Server-to-Server Authentication (OAuth) and Partner Applications in Lync server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md)

</div>

<div>

## <a name="windows-powershell-based-management-and-web-based-management-interface"></a>Administración basada en Windows PowerShell y interfaz de administración basada en Web

Lync Server 2013 proporciona una interfaz de administración eficaz, integrada en la interfaz de línea de comandos de Windows PowerShell. Incluye cmdlets para administración de seguridad, y las características de seguridad de Windows PowerShell se habilitan de manera predeterminada de manera que los usuarios no puedan ejecutar scripts fácilmente o sin saberlo. Esto significa que los valores predeterminados de software se configuran automáticamente de manera que ayuden a maximizar la seguridad y a reducir las vías de ataque. Para obtener más información sobre la compatibilidad con la administración de Windows PowerShell en Lync Server 2013, vea [Lync server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md).

</div>

<div>

## <a name="role-based-access-control-rbac"></a>Control de acceso basado en roles (RBAC)

Microsoft Lync Server 2013 proporciona control de acceso basado en roles (RBAC) para permitirle delegar tareas administrativas y mantener altos estándares de seguridad. Puede usar RBAC para seguir el principio de "privilegios mínimos", donde los usuarios solo reciben los derechos administrativos que requiere su trabajo. Lync Server 2013 introduce la capacidad de crear un nuevo rol y también la capacidad de modificar un rol existente. Para obtener más información, consulte [planeación del control de acceso basado en roles en Lync Server 2013](lync-server-2013-planning-for-role-based-access-control.md).

</div>

</div>

<div>

## <a name="network-address-translation-nat"></a>Traducción de direcciones de red (NAT)

Lync Server 2013 no admite el uso de la traducción de direcciones de red (NAT) en la interfaz interna del servidor perimetral, pero admite la colocación de la interfaz externa del servicio perimetral de acceso, el servicio perimetral de conferencia web y el servicio perimetral A/V detrás de un enrutador o un firewall que realiza la traducción de direcciones Varios servidores perimetrales detrás de un equilibrador de carga de hardware no pueden usar NAT. Si varios servidores perimetrales usan NAT en sus interfaces externas, es necesario el equilibrio de carga del sistema de nombres de dominio (DNS). A su vez, el uso del equilibrio de carga de DNS permite reducir el número de direcciones IP públicas por servidor perimetral en un grupo de servidores perimetrales. Para obtener más información, consulte[planeación del acceso de usuarios externos en Lync Server 2013](lync-server-2013-planning-for-external-user-access.md).

<div>


> [!NOTE]  
> Si se federan con empresas que tienen una implementación de Microsoft Office Communications Server 2007 y es necesario usar audio o vídeo entre la empresa y la empresa federada, los requisitos de puerto serán los de la versión anterior de los servidores perimetrales que se implementan. Por ejemplo, los intervalos de puertos necesarios para las versiones anteriores deben estar abiertos para ambas empresas hasta que el socio federado actualice los servidores perimetrales a Lync Server 2013. En ese momento, los requisitos en materia de puertos se podrán revisar y reducir de acuerdo con la nueva configuración.



</div>

</div>

<div>

## <a name="simplified-certificates-for-edge-servers"></a>Certificados simplificados para servidores perimetrales

El asistente para implementación puede rellenar automáticamente los nombres de sujetos (SN) y los nombres alternativos de sujetos (SAN) para reducir la probabilidad de incluir entradas innecesarias y potencialmente no seguras.

</div>

<div>

## <a name="trustworthy-computing-security-development-lifecycle-sdl"></a>Ciclo de vida de desarrollo de seguridad (SDL) de Trustworthy Computing

Lync Server 2013 se ha diseñado y desarrollado de acuerdo con el ciclo de vida de desarrollo de seguridad (SDL) de Trustworthy Computing <https://go.microsoft.com/fwlink/?linkid=68761>de Microsoft, que se describe en.

  - **** El primer paso en la creación de un sistema de comunicaciones unificadas más seguro es confiar en el diseño de modelos de amenazas y probar cada característica a medida que se diseñó.    Además, Microsoft realiza pruebas fuera del comportamiento diseñado para encontrar las vulnerabilidades de seguridad que se derivan del comportamiento del producto inesperado. Se integraron varias mejoras relacionadas con la seguridad en los procesos y procedimientos de codificación. Las herramientas en tiempo de compilación detectaron la saturación del búfer y otras posibles amenazas para la seguridad antes de que se comprobase el código en el producto final. Naturalmente, es imposible que al diseñar se tengan en cuenta todas las amenazas desconocidas en materia de seguridad. Ningún sistema puede garantizar una total seguridad. Sin embargo, como el desarrollo del producto ha adoptado principios de diseño seguros desde el principio, Lync Server 2013 incorpora tecnologías de seguridad estándar del sector como parte fundamental de su arquitectura.

  - **Digno de confianza**de forma predeterminada, las comunicaciones de red en Lync Server 2013 están cifradas.    Como todos los servidores usan certificados y autenticación Kerberos, TLS, el protocolo de transporte seguro en tiempo real (SRTP) y otras técnicas de cifrado estándar de la industria, incluido el cifrado estándar de cifrado avanzado de 128 bits (AES), virtualmente todos los Lync Los datos del servidor están protegidos en la red. Además, el control de acceso basado en roles permite implementar servidores que ejecutan Lync Server 2013 de modo que cada rol de servidor solo ejecuta los servicios y solo tiene los permisos relacionados con dichos servicios, que son adecuados para la función de servidor.

  - **Confianza por implementación**   toda la documentación de Lync Server 2013 incluye las prácticas recomendadas y las recomendaciones que le ayudarán a determinar y configurar los niveles de seguridad óptimos para su implementación y a evaluar los riesgos de seguridad de activar opciones no predeterminadas.

</div>

</div>

<span> </span>

</div>

</div>

</div>

