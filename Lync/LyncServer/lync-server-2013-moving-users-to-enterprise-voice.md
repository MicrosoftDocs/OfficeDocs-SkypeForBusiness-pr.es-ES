---
title: 'Lync Server 2013: Mover usuarios a telefonía IP empresarial'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Moving users to Enterprise Voice
ms:assetid: a2df6d51-5cf2-4d3e-8f97-496af5fd5e5e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412758(v=OCS.15)
ms:contentKeyID: 48184958
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e92f0a7d71d42d8551a51028afec209e795941d5
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756694"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="moving-users-to-enterprise-voice-in-lync-server-2013"></a>Mover usuarios a telefonía IP empresarial en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-18_

Si va a mover usuarios de una infraestructura de telefonía PBX existente a Enterprise Voice, el proceso de implementación incluye algunos pasos que no forman parte del proceso de planeación ya descrito en [planificación de telefonía IP empresarial en Lync Server 2013](lync-server-2013-planning-for-enterprise-voice.md). Para obtener información sobre cómo migrar usuarios de una implementación de voz de empresa anterior, consulte los documentos de migración que se incluyeron con los medios de instalación.

El proceso de mover usuarios de una infraestructura de telefonía existente a Enterprise Voice consta de los siguientes pasos:

1.  Designar números de teléfono principales.

2.  Habilitar a los usuarios para Enterprise Voice.

3.  Preparar planes de marcado para los usuarios.

4.  Planear las directivas de voz de usuario.

5.  Planificar rutas de llamadas.

6.  Configure el tronco de PBX o SIP para redirigir las llamadas para los usuarios habilitados para telefonía IP empresarial.

7.  Mover usuarios a mensajería unificada (UM) de Exchange (recomendado).

En este tema se describe la planificación necesaria para cada uno de estos pasos.

<div>

## <a name="step-1-designate-primary-phone-numbers"></a>Paso 1. Designar números de teléfono principales

Enterprise Voice integra voz con otros medios de mensajería, como cuando una llamada llega al servidor, el servidor asigna el número al URI SIP del usuario y, después, bifurca la llamada a todos los puntos de conexión de cliente asociados con ese SIP-URI. Este proceso requiere que cada usuario esté asociado a un número de teléfono principal.

Un número de teléfono principal debe ser:

  - Único globalmente o, en el caso de las extensiones internas, exclusiva de la empresa.

  - Pertenece a la empresa y se pueda enrutar. No se deben usar números personales.

Los usuarios de la empresa pueden tener dos o más números de teléfono que se indican en servicios de dominio de Active Directory. Todos los números de teléfono asociados con un usuario en particular se pueden ver o cambiar en la hoja de propiedades de ese usuario en el complemento usuarios y equipos de Active Directory.

El cuadro **número de teléfono** en la pestaña **General** del cuadro de diálogo Propiedades del **usuario** debe contener el número de trabajo principal del usuario. Este número normalmente se designará como número de teléfono principal del usuario.

Es posible que algunos usuarios tengan requisitos especiales (por ejemplo, un ejecutivo que quiera que todas las llamadas entrantes se dirijan a través de un auxiliar administrativo), pero dichas excepciones deben limitarse a aquellos casos en los que la necesidad sea clara y crítica.

Una vez que se elige un número principal, debe ser:

  - Normalizado al formato E. 164, siempre que sea posible.

  - Se ha copiado en el atributo de **msRTCSIP-line de** Active Directory.
    
    <div>
    

    > [!NOTE]  
    > <STRONG>Coexistencia con control remoto de llamadas (RCC)</STRONG><BR>RCC es la capacidad de usar Lync Server para supervisar y controlar un teléfono PBX de escritorio. El control se enruta a través del servidor, que actúa como una puerta de enlace a la PBX. Aunque no puede configurar un usuario tanto para RCC como para telefonía IP empresarial, la configuración de URI de línea designa el número de teléfono principal de un usuario en cualquier caso.<BR>Si ya tiene una infraestructura PBX existente que quiere que los usuarios seleccionados puedan seguir usando, puede introducir una voz empresarial incremental en la organización. Para obtener más información sobre este escenario de implementación, consulte <A href="lync-server-2013-direct-sip-deployment-options.md">Opciones de implementación de SIP directo en Lync Server 2013</A> en la documentación de planeación.<BR>En versiones anteriores, se podía habilitar tanto RCC como empresarial Voice para un usuario, pero solo si también has configurado el usuario para la bifurcación dual, una característica en la que una llamada entrante sonará al teléfono PBX de un usuario y a Communicator al mismo tiempo. En Lync Server 2010, no se admite la bifurcación dual.

    
    </div>

Hay tres métodos para rellenar el atributo **msRTCSIP-line** :

  - Microsoft Identity Integration Server (recomendado)

  - Página **usuarios** del panel de control de Lync Server

Desde dónde se deben procesar muchos números de teléfono, la mejor opción es una secuencia de comandos personalizada desarrollada por su organización. Según el modo en que la organización represente los números de teléfono en los servicios de dominio de Active Directory, es posible que la secuencia de comandos tenga que normalizar los números de teléfono principales al formato E. 164 antes de copiarlos en el atributo de **msRTCSIP-line** .

  - Si su organización mantiene todos los números de teléfono en los servicios de dominio de Active Directory en un solo formato y este formato es E. 164, su script solo necesita escribir cada número de teléfono principal en el atributo **msRTCSIP-line** .

  - Si su organización mantiene todos los números de teléfono en los servicios de dominio de Active Directory en un solo formato, pero ese formato no es E. 164, su script debe definir una regla de normalización adecuada para convertir los números de teléfono principales de su formato existente a E. 164 antes de escribirlos en el atributo de **msRTCSIP-line** .

  - Si su organización no exige un formato estándar para los números de teléfono de los servicios de dominio de Active Directory, su script debe definir las reglas de normalización apropiadas para convertir los números de teléfono principales de los distintos formatos a E. 164 conformidad antes de escribir los números de teléfono principales en el atributo **msRTCSIP-line** .

El script también tendrá que insertar el prefijo **Tel:** antes de cada número principal antes de escribirlo en el atributo de **msRTCSIP-line** .

El formato esperado del número especificado en este atributo es:

  - Tel: + 14255550100; ext = 50100.

  - Tel: 5550100 (para extensiones exclusivas de toda la empresa)
    
    <div>
    

    > [!IMPORTANT]  
    > La normalización realizada por el servicio de libreta de direcciones (ABS) no reemplaza o elimina la necesidad de normalizar el número de teléfono principal de cada usuario en servicios de dominio de Active Directory porque ABS no tiene acceso a los servicios de dominio de Active Directory y, por lo tanto, no puede copiar números principales en el atributo <STRONG>msRTCSIP-line</STRONG> .

    
    </div>

</div>

<div>

## <a name="step-2-enable-users-for-enterprise-voice"></a>Paso 2. Habilitar a los usuarios para la telefonía IP empresarial

Aparte de identificar qué usuarios se deben habilitar, no es necesario realizar ninguna planificación especial para completar este paso.

</div>

<div>

## <a name="step-3-prepare-dial-plans-for-users"></a>Paso 3. Preparar planes de marcado para los usuarios.

Los usuarios que están habilitados para telefonía IP empresarial no podrán llamar a la llamada a la RTC sin realizar planes de marcado. Un plan de marcado es un conjunto de reglas de normalización especificado por el usuario que convierte números de teléfono para una ubicación especificada por el usuario, un usuario individual o un objeto de contacto a un formato estándar único (E.164) con fines de autorización telefónica y enrutamiento de llamadas. Las reglas de normalización definen la forma en que los números de teléfono expresados en diversos formatos se van a redirigir en cada ubicación, usuario u objeto de contacto que se haya especificado.

Para obtener información sobre la preparación de los planes de marcado, consulte [planes de marcado y reglas de normalización en Lync Server 2013](lync-server-2013-dial-plans-and-normalization-rules.md).

</div>

<div>

## <a name="step-4-plan-user-voice-policies"></a>Paso 4. Planear las directivas de voz de usuario

La configuración de clase de usuario de servicio en un sistema PBX heredado, como el derecho de hacer llamadas de larga distancia o internacionales desde teléfonos de la empresa, debe ser reconfigurada como directivas de VoIP para los usuarios que han migrado a la telefonía IP empresarial. Para obtener más información sobre la planeación y la creación de directivas para telefonía IP empresarial, consulte [directivas de voz en Lync Server 2013](lync-server-2013-voice-policies.md).

</div>

<div>

## <a name="step-5-plan-outbound-call-routes"></a>Paso 5. Planificar rutas de llamadas salientes

Las rutas de llamadas especifican cómo Lync Server administra las llamadas salientes que hacen los usuarios de telefonía IP. Cuando un usuario marca un número, el servidor, si es necesario, normaliza la cadena de marcado al formato E. 164 e intenta hacerlo coincidir con el URI del SIP. Si el servidor no puede establecer la coincidencia, aplica la lógica de enrutamiento de llamadas salientes en función del número. El último paso para definir esa lógica es crear una ruta de llamada con nombre diferente para cada conjunto de números de teléfono de destino que aparecen en cada plan de marcado.

Para obtener más información sobre la planeación de rutas de llamadas, consulte [rutas de voz en Lync Server 2013](lync-server-2013-voice-routes.md).

</div>

<div>

## <a name="step-6-configure-pbx-or-sip-trunk-to-reroute-calls-for-enterprise-voice-users"></a>Paso 6. Configurar el tronco de PBX o SIP para redirigir llamadas para usuarios de Enterprise Voice

Los usuarios que anteriormente se hospedaban en una PBX tradicional o en una conexión SIP troncal a un proveedor de servicios de telefonía por Internet (ITSP) conservan sus números de teléfono después del movimiento. El único requisito es que, después de la mudanza, el troncal de PBX o SIP debe reconfigurarse para enrutar las llamadas entrantes para los usuarios de la empresa de telefonía al servidor de mediación.

</div>

<div>

## <a name="step-7-move-users-to-exchange-unified-messaging-recommended"></a>Paso 7. Mover usuarios a la mensajería unificada de Exchange (recomendado)

El traslado de usuarios a la mensajería unificada de Exchange consta de las siguientes tareas:

  - Configure la mensajería unificada de Exchange y Lync Server para que funcionen conjuntamente.

  - Habilite los usuarios para la respuesta de la mensajería unificada de Exchange y Outlook Voice Access. Esta tarea se realiza en el servidor de mensajería unificada de Exchange. Para obtener más información, consulte la biblioteca de TechNet de [http://go.microsoft.com/fwlink/p/?linkID=139372](http://go.microsoft.com/fwlink/p/?linkid=139372)Exchange Server 2010 en.

</div>

</div>

<span> </span>

</div>

</div>

</div>

