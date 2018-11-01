---
title: 'Lync Server 2013: Mover usuarios a telefonía IP empresarial'
TOCTitle: Mover usuarios a telefonía IP empresarial
ms:assetid: a2df6d51-5cf2-4d3e-8f97-496af5fd5e5e
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg412758(v=OCS.15)
ms:contentKeyID: 48276178
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Mover usuarios a telefonía IP empresarial en Lync Server 2013

 

_**Última modificación del tema:** 2016-12-08_

Si va a mover usuarios de una infraestructura de telefonía RTC existente a Telefonía IP empresarial, el proceso de implementación incluye algunos pasos que no forman parte del proceso de planeamiento descrito en la sección [Planear la telefonía IP empresarial en Lync Server 2013](lync-server-2013-planning-for-enterprise-voice.md). Para obtener información sobre la migración de usuarios de una implementación de Telefonía IP empresarial anterior, consulte la documentación sobre migración incluida con el disco de instalación.

El proceso de mover a los usuarios de una infraestructura de telefonía existente a Telefonía IP empresarial consta de los siguientes pasos:

1.  Designar los números de teléfono principales.

2.  Habilitar a los usuarios para Telefonía IP empresarial.

3.  Preparar planes de marcado para los usuarios.

4.  Planear las directivas de voz de los usuarios.

5.  Planear rutas de llamadas.

6.  Configurar el sistema PBX o el tronco SIP de modo que vuelva a enrutar las llamadas de los usuarios habilitados para Enterprise Voice.

7.  Mover los usuarios a Mensajería unificada de Exchange (UM) (se recomienda).

En este tema se describe cómo planear cada uno de estos pasos.

## Paso 1. Designar los números de teléfono principales

Telefonía IP empresarial integra la voz con otros medios de mensajería de forma que, cuando una llamada entrante llega al servidor, este asigne el número al URI de SIP del usuario y, a continuación, bifurque la llamada a todos los extremos del cliente asociados a dicho URI de SIP. Este proceso requiere que cada usuario esté asociado a un número de teléfono principal.

Un número de teléfono principal debe ser:

  - Único a escala mundial o, en el caso de las extensiones internas, único en la empresa.

  - Propiedad de la empresa y enrutable en la empresa. No deben usarse números personales.

Los usuarios corporativos pueden tener dos o más números de teléfono en el Servicios de dominio de Active Directory. Todos los números de teléfono asociados a un usuario determinado se pueden ver o modificar en la hoja de propiedades de dicho usuario en el complemento Usuarios y equipos de Active Directory.

El cuadro de texto **Número de teléfono** de la pestaña **General** del cuadro de diálogo **Propiedades del usuario** debe contener el número principal del trabajo del usuario. Normalmente, este número se designará como número de teléfono principal del usuario.

Algunos usuarios pueden tener requisitos especiales (por ejemplo, un directivo que desea que todas las llamadas recibidas se enruten a través de un asistente administrativo), pero esas excepciones deben limitarse únicamente a aquellos usuarios cuyas necesidades sean claras y de vital importancia.

Una vez elegido el número principal, se debe:

  - Normalizar al formato E.164, cuando sea posible.

  - Copiarlo en el atributo **msRTCSIP-line** de Active Directory.
    

    > [!NOTE]
    > <STRONG>Coexistencia con el control remoto de llamadas (RCC)</STRONG><BR>RCC permite usar Lync Server para supervisar y controlar un teléfono PBX de escritorio. El control se enruta a través del servidor, que actúa como puerta de enlace al sistema PBX. A pesar de que no puede configurar un usuario para RCC y para Telefonía IP empresarial, el valor de URI de línea designa el número de teléfono principal de un usuario en ambos casos.<BR>Si ya dispone de una infraestructura PBX que desea que sigan usando los usuarios seleccionados, puede introducir Telefonía IP empresarial de forma gradual en su organización. Para obtener información sobre este escenario de implementación, consulte <A href="lync-server-2013-direct-sip-deployment-options.md">Opciones de implementación SIP directa en Lync Server 2013</A> en la documentación sobre planeamiento.<BR>En versiones anteriores, era posible habilitar tanto RCC como Telefonía IP empresarial para un mismo usuario, pero únicamente si también se configuraba el usuario para la bifurcación doble, una característica mediante la cual una llamada entrante suena al mismo tiempo en el teléfono PBX de un usuario y en Communicator. En Lync Server 2010, la bifurcación doble no está admitida.



Hay tres métodos para rellenar el atributo **msRTCSIP-line**:

  - Microsoft Identity Integration Server (se recomienda)

  - La página **Usuarios** en el Panel de control de Lync Server

Cuando hay que procesar muchos números de teléfono, la mejor opción es usar un script desarrollado de forma personalizada por su organización. Dependiendo de la forma en que la organización represente los números de teléfono en los Servicios de dominio de Active Directory, es posible que el script tenga que normalizar los números de teléfono principales según el formato E.164 antes de copiarlos en el atributo **msRTCSIP-line**.

  - Si la organización mantiene todos los números de teléfono de los Servicios de dominio de Active Directory en un único formato y ese formato es E.164, el script solo deberá escribir cada número de teléfono principal en el atributo **msRTCSIP-line**.

  - Si la organización mantiene todos los números de teléfono de los Servicios de dominio Active Directory en un único formato, pero ese formato no es E.164, el script deberá definir una regla de normalización adecuada para convertir los números de teléfono principales al formato E.164 antes de escribirlos en el atributo **msRTCSIP-line**.

  - Si la organización no exige ningún formato estándar para los números de teléfono de los Servicios de dominio de Active Directory, el script deberá definir reglas de normalización adecuadas para convertir los distintos formatos de los números de teléfono principales al formato E.164 antes de escribirlos en el atributo **msRTCSIP-line**.

El script también deberá insertar el prefijo **Tel:** delante de cada número principal antes de escribirlo en el atributo **msRTCSIP-line**.

El formato esperado del número especificado en este atributo es:

  - Tel:+14255550100;ext=50100.

  - Tel:5550100 (para extensiones únicas en toda la empresa)
    
    > [!IMPORTANT]  
    > La normalización realizada por el servicio de libreta de direcciones (ABS) no reemplaza ni elimina de ningún otro modo la necesidad de normalizar el número de teléfono principal de cada usuario en los Servicios de dominio de Active Directory porque ABS carece de acceso a Active Directory y, por lo tanto, no puede copiar los números principales en el atributo <strong>msRTCSIP-line</strong>.
    


## Paso 2. Habilitar a los usuarios para Enterprise Voice

Aparte de identificar a los usuarios que se van a habilitar, no se requiere ninguna otra planeación especial para llevar a cabo este paso.

## Paso 3. Preparar planes de marcado para los usuarios.

Los usuarios que estén habilitados para Telefonía IP empresarial no podrán realizar llamadas a la RTC si no hay planes de marcado. Un plan de marcado es un conjunto de reglas de normalización especificado por el usuario que convierte números de teléfono para una ubicación especificada por el usuario, un usuario individual o un objeto de contacto a un formato estándar único (E.164) con fines de autorización telefónica y enrutamiento de llamadas. Las reglas de normalización definen la forma en que los números de teléfono expresados en diversos formatos se van a enrutar en cada ubicación, usuario u objeto de contacto que se haya especificado.

Para obtener más información sobre la preparación de planes de marcado, consulte la sección [Planes de marcado y reglas de normalización en Lync Server 2013](lync-server-2013-dial-plans-and-normalization-rules.md).

## Paso 4. Planear las directivas de voz de los usuarios

Las clases de servicio de los usuarios en un sistema PBX heredado, como el derecho a realizar llamadas de larga distancia o llamadas internacionales desde teléfonos de la compañía, deben volver a configurarse como directivas VoIP para los usuarios que se pasen a Enterprise Voice. Si desea obtener información detallada sobre la planeación y la creación de directivas para Enterprise Voice, consulte [Directivas de voz en Lync Server 2013](lync-server-2013-voice-policies.md).

## Paso 5. Planear rutas de llamadas salientes

Las rutas de llamadas especifican la forma en que Lync Server administra las llamadas salientes realizadas por usuarios de Enterprise Voice. Cuando un usuario marca un número, el servidor normaliza la cadena de marcado al formato E.164, si es necesario, e intenta establecer una coincidencia con un URI de SIP. Si el servidor no puede establecer esa coincidencia, aplicará la lógica de enrutamiento de llamadas salientes basándose en el número. El paso final para definir la lógica consiste en crear una ruta de llamada con nombre independiente para cada conjunto de números de teléfono de destino indicados en cada plan de marcado.

Para obtener información detallada sobre cómo planear rutas de llamadas, consulte [Rutas de voz en Lync Server 2013](lync-server-2013-voice-routes.md).

## Paso 6. Configurar el sistema PBX o el tronco SIP para volver a enrutar las llamadas de los usuarios de Enterprise Voice

Los usuarios que anteriormente se hospedaban en una conexión tradicional PBX o en una conexión basada en troncos SIP con un proveedor de servicios de telefonía por Internet (ITSP) conservan su número de teléfono después del traslado. El único requisito tras el traslado es que el sistema PBX o el tronco SIP debe volver a configurarse de forma que enrute las llamadas entrantes para los usuarios de Telefonía IP empresarial al Servidor de mediación.

## Paso 7. Mover los usuarios a la mensajería unificada de Exchange (se recomienda)

Para mover a los usuarios a la Mensajería unificada de Exchange, deben realizarse estas tareas:

  - Configurar la mensajería unificada de Exchange y Lync Server para que trabajen conjuntamente.

  - Habilitar a los usuarios para el contestador automático de la Mensajería unificada de Exchange y Outlook Voice Access. Esta tarea se realiza en el servidor de Mensajería unificada de Exchange. Para obtener información detallada, consulte la biblioteca de TechNet de Exchange Server 2010 en [http://go.microsoft.com/fwlink/?linkid=139372\&clcid=0xC0A](http://go.microsoft.com/fwlink/?linkid=139372%26clcid=0xc0a).

