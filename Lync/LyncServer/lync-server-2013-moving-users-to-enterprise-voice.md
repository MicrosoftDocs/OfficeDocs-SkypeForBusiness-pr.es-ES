---
title: 'Lync Server 2013: mover usuarios a telefonía IP empresarial'
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
ms.openlocfilehash: 968e70e74cd129f05d4f39f626d9e21b1c3dc33a
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42131153"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="moving-users-to-enterprise-voice-in-lync-server-2013"></a>Mover usuarios a telefonía IP empresarial en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-18_

Si va a mover usuarios de una infraestructura de telefonía PBX existente a Enterprise Voice, el proceso de implementación incluye algunos pasos que no forman parte del proceso de planeación ya descrito en [Planning for Enterprise Voice in Lync Server 2013](lync-server-2013-planning-for-enterprise-voice.md). Para obtener información sobre la migración de usuarios de una implementación de telefonía IP empresarial anterior, vea los documentos de migración que se incluyeron en los medios de instalación.

El proceso de traslado de usuarios de una infraestructura de telefonía existente a Enterprise Voice consta de los siguientes pasos:

1.  Designar los números de teléfono principales.

2.  Habilitar a los usuarios para Enterprise Voice.

3.  Preparar planes de marcado para los usuarios.

4.  Planeación de directivas de voz de usuario.

5.  Planeación de rutas de llamadas.

6.  Configure PBX o el tronco SIP para redirigir las llamadas de los usuarios habilitados para telefonía IP empresarial.

7.  Mover usuarios a mensajería unificada (UM) de Exchange (recomendado).

En este tema se describe la planeación necesaria para cada uno de estos pasos.

<div>

## <a name="step-1-designate-primary-phone-numbers"></a>Paso 1. Designar los números de teléfono principales

La telefonía IP empresarial se integra con otros medios de mensajería, de modo que cuando una llamada entrante llega al servidor, el servidor asigna el número al URI SIP del usuario y, a continuación, se ramifica la llamada a todos los extremos de cliente asociados con ese SIP-URI. Este proceso requiere que cada usuario esté asociado a un número de teléfono principal.

Un número de teléfono principal debe ser:

  - Globalmente único o, en el caso de las extensiones internas, única en la empresa.

  - Propiedad de y enrutable de la empresa. No se deben usar números personales.

Los usuarios de la empresa pueden tener dos o más números de teléfono enumerados para ellos en los servicios de dominio de Active Directory. Todos los números de teléfono asociados con un usuario en particular se pueden ver o cambiar en la hoja de propiedades de ese usuario en el complemento usuarios y equipos de Active Directory.

El cuadro **número de teléfono** de la ficha **General** del cuadro de diálogo Propiedades de **usuario** debe contener el número de trabajo principal del usuario. Este número se suele designar como el número de teléfono principal del usuario.

Es posible que algunos usuarios tengan requisitos especiales (por ejemplo, un ejecutivo que quiera que todas las llamadas entrantes se enruten a través de un asistente administrativo), pero esas excepciones deben limitarse a aquellas en las que la necesidad sea clara y crítica.

Una vez seleccionado un número principal, debe ser:

  - Normalizado al formato E. 164, siempre que sea posible.

  - Se copia en el atributo **msRTCSIP-line de** Active Directory.
    
    <div>
    

    > [!NOTE]  
    > <STRONG>Coexistencia con control remoto de llamadas (RCC)</STRONG><BR>RCC es la capacidad de usar Lync Server para supervisar y controlar un teléfono PBX de escritorio. El control se enruta a través del servidor, que actúa como una puerta de enlace a la PBX. Aunque no se puede configurar un usuario tanto para RCC como para telefonía IP empresarial, la configuración de URI de línea designa el número de teléfono principal de un usuario en cualquier caso.<BR>Si tiene una infraestructura PBX existente que desea que los usuarios seleccionados sigan usando, puede presentar la telefonía IP empresarial de forma incremental en su organización. Para obtener más información sobre este escenario de implementación, consulte <A href="lync-server-2013-direct-sip-deployment-options.md">Opciones de implementación SIP directa en Lync Server 2013</A> en la documentación referente a la planeación.<BR>En versiones anteriores, podía habilitar tanto RCC como Enterprise Voice para un usuario, pero solo si también configuraste el usuario para dos ramificaciones, una característica en la que una llamada entrante sonará simultáneamente por teléfono PBX de usuario y Communicator. En Lync Server 2010, no se admite la bifurcación dual.

    
    </div>

Hay tres métodos para rellenar el atributo **msRTCSIP-line** :

  - Microsoft Identity Integration Server (recomendado)

  - Página **usuarios** del panel de control de Lync Server

Cuando se deben procesar muchos números de teléfono, la mejor opción es una secuencia de comandos personalizada desarrollada por la organización. En función de cómo represente su organización los números de teléfono en los servicios de dominio de Active Directory, es posible que el script deba normalizar los números de teléfono principales al formato E. 164 antes de copiarlos al atributo **msRTCSIP-line** .

  - Si su organización mantiene todos los números de teléfono de los servicios de dominio de Active Directory en un único formato y, si ese formato es E. 164, el script solo tiene que escribir cada número de teléfono principal en el atributo **msRTCSIP-line** .

  - Si la organización mantiene todos los números de teléfono de los servicios de dominio de Active Directory en un único formato, pero ese formato no es E. 164, el script debe definir una regla de normalización adecuada para convertir los números de teléfono principales de su formato existente a E. 164 antes de escribirlos en el atributo **msRTCSIP-line** .

  - Si su organización no exige un formato estándar para los números de teléfono de los servicios de dominio de Active Directory, el script debe definir las reglas de normalización adecuadas para convertir los números de teléfono principales de los distintos formatos a E. 164 cumplimiento antes de escribir los números de teléfono principales en el atributo **msRTCSIP-line** .

El script también tendrá que insertar el prefijo **Tel:** antes de cada número principal antes de escribirlo en el atributo **msRTCSIP-line** .

El formato esperado del número especificado en este atributo es:

  - Tel: + 14255550100; ext = 50100.

  - Tel: 5550100 (para extensiones únicas de toda la empresa)
    
    <div>
    

    > [!IMPORTANT]  
    > La normalización que realiza el servicio de libreta de direcciones (ABS) no reemplaza o elimina la necesidad de normalizar el número de teléfono principal de cada usuario en servicios de dominio de Active Directory porque el ABS no tiene acceso a los servicios de dominio de Active Directory y, por lo tanto, no puede copiar los números principales en el atributo <STRONG>msRTCSIP-line</STRONG> .

    
    </div>

</div>

<div>

## <a name="step-2-enable-users-for-enterprise-voice"></a>Paso 2. Habilitar a los usuarios para la telefonía IP empresarial

Aparte de identificar los usuarios que se van a habilitar, no se requiere una planificación especial para completar este paso.

</div>

<div>

## <a name="step-3-prepare-dial-plans-for-users"></a>Paso 3. Preparar planes de marcado para los usuarios.

Los usuarios habilitados para la telefonía IP empresarial no podrán realizar llamadas a la RTC sin planes de marcado en su lugar. Un plan de marcado es un conjunto de reglas de normalización especificado por el usuario que convierte números de teléfono para una ubicación especificada por el usuario, un usuario individual o un objeto de contacto a un formato estándar único (E.164) con fines de autorización telefónica y enrutamiento de llamadas. Las reglas de normalización definen la forma en que los números de teléfono expresados en diversos formatos se van a enrutar en cada ubicación, usuario u objeto de contacto que se haya especificado.

Para obtener información sobre la preparación de planes de marcado, consulte [planes de marcado y reglas de normalización en Lync Server 2013](lync-server-2013-dial-plans-and-normalization-rules.md).

</div>

<div>

## <a name="step-4-plan-user-voice-policies"></a>Paso 4. Planeación de directivas de voz de usuario

La configuración de la clase de servicio de usuario en una PBX heredada, como el derecho de realizar llamadas de larga distancia o internacionales desde los teléfonos de la empresa, debe volver a configurarse como directivas VoIP para los usuarios que se movieron a la telefonía IP empresarial. Para obtener más información sobre la planeación y la creación de directivas para la telefonía IP empresarial, consulte [directivas de voz en Lync Server 2013](lync-server-2013-voice-policies.md).

</div>

<div>

## <a name="step-5-plan-outbound-call-routes"></a>Paso 5. Planeación de rutas de llamadas salientes

Las rutas de llamadas especifican cómo Lync Server administra las llamadas salientes realizadas por los usuarios de telefonía IP empresarial. Cuando un usuario marca un número, el servidor, si es necesario, normaliza la cadena de marcado al formato E. 164 e intenta establecer una coincidencia con un URI de SIP. Si el servidor no puede realizar la coincidencia, aplica la lógica de enrutamiento de llamadas salientes en función del número. El último paso para definir la lógica es crear una ruta de llamada con nombre independiente para cada conjunto de números de teléfono de destino que se enumeran en cada plan de marcado.

Para obtener más información sobre la planeación de rutas de llamadas, consulte [rutas de voz en Lync Server 2013](lync-server-2013-voice-routes.md).

</div>

<div>

## <a name="step-6-configure-pbx-or-sip-trunk-to-reroute-calls-for-enterprise-voice-users"></a>Paso 6. Configurar la PBX o el tronco SIP para redirigir las llamadas de los usuarios de Enterprise Voice

Los usuarios que anteriormente se hospedaban en una PBX tradicional o en una conexión de enlace troncal SIP a un proveedor de servicios de telefonía por Internet (ITSP) conservan sus números de teléfono después del traslado. El único requisito es que, después del traslado, el tronco de PBX o de SIP se debe volver a configurar para enrutar las llamadas entrantes de los usuarios de Enterprise Voice al servidor de mediación.

</div>

<div>

## <a name="step-7-move-users-to-exchange-unified-messaging-recommended"></a>Paso 7. Mover usuarios a la mensajería unificada de Exchange (recomendado)

El traslado de usuarios a la mensajería unificada de Exchange consta de las siguientes tareas:

  - Configurar la mensajería unificada de Exchange y Lync Server para que funcionen conjuntamente.

  - Habilite a los usuarios para el contestador automático de mensajería unificada de Exchange y Outlook Voice Access. Esta tarea se realiza en el servidor de mensajería unificada de Exchange. Para obtener más información, consulte la biblioteca de TechNet de [https://go.microsoft.com/fwlink/p/?linkID=139372](https://go.microsoft.com/fwlink/p/?linkid=139372)Exchange Server 2010 en.

</div>

</div>

<span> </span>

</div>

</div>

</div>

