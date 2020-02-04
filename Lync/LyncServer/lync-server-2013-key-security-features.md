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
ms.openlocfilehash: 55d59a6978b90db82ccf899df90b05c739e71a57
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41738320"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="key-security-features-in-lync-server-2013"></a>Características de seguridad clave de Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-07-18_

Lync Server 2013 incluye varias características de seguridad, entre las que se incluyen la autenticación de servidor a servidor, el control de acceso basado en roles y el almacenamiento centralizado de los datos de configuración.

Este artículo proporciona información general de alto nivel sobre la seguridad de Lync Server 2013.

<div>

## <a name="key-security-features-in-lync-server-2013"></a>Características de seguridad clave de Lync Server 2013

La seguridad es un tema muy amplio. La seguridad alcanza todas las características de Lync Server 2013, así como las bases de datos, los servicios y el hardware que componen un ecosistema de Lync. En este artículo, se describen algunas de las características de Lync Server 2013 especialmente diseñadas para la seguridad.

<div>

## <a name="planning-and-design-tools"></a>Herramientas de planeación y diseño

Lync Server 2013 ofrece dos herramientas para facilitar la planeación y el diseño y reducir la posibilidad de que se configuren los componentes de Lync Server.

  - La **herramienta de planeación** de la topología automatiza gran parte del proceso de diseño de la topología. Puede exportar los resultados de la herramienta de planeación a Topology Builder, que es la herramienta necesaria para instalar cada servidor que ejecute Lync Server 2013.

  - El **Generador de topologías** almacena toda la información de configuración en el almacén de administración central.

Para obtener más información sobre estas herramientas, consulte [planificación de Lync Server 2013](lync-server-2013-planning.md).

</div>

<div>

## <a name="central-management-store"></a>Almacén de administración central

En Lync Server 2013, los datos de configuración de los servidores y los servicios forman parte del almacén central de administración. El almacén central de administración proporciona un sólido almacenamiento schematized de los datos necesarios para definir, configurar, mantener, administrar, describir y utilizar una implementación de Lync Server. También comprueba los datos para asegurarse de que la configuración es coherente. Todos los cambios realizados a esta configuración se producen en el almacén de administración central, excepto los problemas de "sin sincronizar".

Las copias de solo lectura de los datos se replican en todos los servidores de la topología, incluyendo los servidores perimetrales y las aplicaciones de sucursal con funciones de supervivencia. Un servicio que se ejecuta de forma predeterminada en el contexto del servicio de red es el encargado de administrar la replicación, de modo que los permisos y derechos se reducen a los de un simple usuario del equipo.

</div>

<div>

## <a name="server-to-server-authentication"></a>Autenticación de servidor a servidor

En Lync Server 2013, se puede configurar la autenticación entre servidores mediante el protocolo de autorización abierta (OAuth). Por ejemplo, puede configurar Lync Server 2013 para que se autentique con un servidor que ejecute Exchange Server 2013. Con el protocolo OAuth, Lync Server y el servidor Exchange pueden confiar entre sí. Esto proporciona la posibilidad de integrar los productos de forma sencilla. Para obtener más información, vea [administrar la autenticación de servidor a servidor (OAuth) y las aplicaciones de socio en Lync server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md)

</div>

<div>

## <a name="windows-powershell-based-management-and-web-based-management-interface"></a>Administración basada en Windows PowerShell e interfaz de administración basada en web

Lync Server 2013 ofrece una interfaz de administración eficaz, creada en la interfaz de línea de comandos de Windows PowerShell. Incluye cmdlets para administración de seguridad, y las características de seguridad de Windows PowerShell se habilitan de manera predeterminada de manera que los usuarios no puedan ejecutar scripts fácilmente o sin saberlo. Esto significa que los valores predeterminados de software se configuran automáticamente de manera que ayuden a maximizar la seguridad y a reducir las vías de ataque. Para obtener más información sobre la compatibilidad de administración de Windows PowerShell en Lync Server 2013, vea [consola de administración de Lync server 2013](lync-server-2013-lync-server-management-shell.md).

</div>

<div>

## <a name="role-based-access-control-rbac"></a>Control de acceso basado en roles (RBAC)

Microsoft Lync Server 2013 ofrece control de acceso basado en roles (RBAC) que permite delegar tareas administrativas a la vez que se mantienen los altos estándares de seguridad. Puede usar RBAC para seguir el principio de "privilegios mínimos", donde los usuarios solo reciben los derechos administrativos que requiere su trabajo. Lync Server 2013 introduce la capacidad de crear un nuevo rol y también la capacidad de modificar un rol existente. Para obtener más información, vea [planificación de control de acceso basado en roles en Lync Server 2013](lync-server-2013-planning-for-role-based-access-control.md).

</div>

</div>

<div>

## <a name="network-address-translation-nat"></a>Traducción de direcciones de red (NAT)

Lync Server 2013 no admite el uso de la traducción de direcciones de red (NAT) en la interfaz interna del servidor perimetral, pero admite la colocación de la interfaz externa del servicio perimetral de acceso, el servicio perimetral de conferencias web y el servicio perimetral A/V detrás de un enrutador o firewall que realice la traducción de direcciones de red Si hay varios servidores perimetrales tras un equilibrador de carga de hardware, no se podrá utilizar NAT. Si hay varios servidores perimetrales que utilizan NAT en sus interfaces externas, se necesitará aplicar equilibrio de carga de sistema de nombres de dominio (DNS). El equilibrio de carga de DNS permite, al mismo tiempo, reducir el número de direcciones IP públicas por servidor perimetral en grupo de servidores perimetrales. Para obtener más información, consulte[planear el acceso de usuarios externos en Lync Server 2013](lync-server-2013-planning-for-external-user-access.md).

<div>


> [!NOTE]  
> Si su empresa se federa con otra que tenga una implementación de Microsoft Office Communications Server 2007 y necesita utilizar audio/vídeo entre su empresa y la empresa federada, los requisitos de los puertos serán los correspondientes a la versión antigua de servidores perimetrales que se haya implementado. Por ejemplo, los intervalos de puertos necesarios para esas versiones anteriores deben abrirse en ambas empresas hasta que el socio federado actualice sus servidores perimetrales a Lync Server 2013. En ese momento, los requisitos en materia de puertos se podrán revisar y reducir de acuerdo con la nueva configuración.



</div>

</div>

<div>

## <a name="simplified-certificates-for-edge-servers"></a>Certificados simplificados para servidores perimetrales

El asistente para implementación puede rellenar automáticamente los nombres de sujetos (SN) y los nombres alternativos de sujetos (SAN) para reducir la probabilidad de incluir entradas innecesarias y potencialmente no seguras.

</div>

<div>

## <a name="trustworthy-computing-security-development-lifecycle-sdl"></a>Ciclo de vida de desarrollo de seguridad (SDL) de Trustworthy Computing

Lync Server 2013 se ha diseñado y desarrollado en conformidad con el ciclo de vida de desarrollo de seguridad de Microsoft Trustworthy Computing (SDL <http://go.microsoft.com/fwlink/?linkid=68761>), que se describe en.

  - **Confianza por diseño**   el primer paso en la creación de un sistema de comunicaciones unificado más seguro era diseñar modelos de amenazas y probar cada característica tal como se diseñó. Además, Microsoft realiza pruebas fuera del comportamiento diseñado para encontrar vulnerabilidades de seguridad derivadas del comportamiento inesperado del producto. Se incorporaron muchas mejoras relacionadas con la seguridad, tanto al proceso como a las prácticas de codificación. Las herramientas de tiempo de compilación detectan excesos de almacenaje y otras amenazas de seguridad antes de que el código se incorpore al producto final. Obviamente, es imposible realizar diseños contra amenazas de seguridad desconocidas. Ningún sistema puede garantizar la seguridad total. Sin embargo, dado que el desarrollo del producto ha adoptado principios de diseño seguros desde el principio, Lync Server 2013 incorpora tecnologías de seguridad estándar del sector como parte fundamental de su arquitectura.

  - **Digno de confianza**de forma predeterminada, las comunicaciones de red en Lync Server 2013 están cifradas.    Como todos los servidores usan certificados y autenticación Kerberos, TLS, protocolo seguro de transporte en tiempo real (SRTP) y otras técnicas de cifrado estándar de la industria, incluido el cifrado estándar de cifrado avanzado de 128 bits (AES), casi todas las Lync Los datos del servidor están protegidos en la red. Además, el control de acceso basado en roles permite implementar servidores que ejecuten Lync Server 2013 para que cada rol de servidor solo ejecute los servicios y solo tenga los permisos relacionados con esos servicios, que son adecuados para el rol de servidor.

  - **Confianza por implementación**   toda la documentación de Lync Server 2013 incluye prácticas recomendadas y recomendaciones que le ayudarán a determinar y configurar los niveles de seguridad óptimos para su implementación y a evaluar los riesgos de seguridad de activar opciones no predeterminadas.

</div>

</div>

<span> </span>

</div>

</div>

</div>

