---
title: 'Lync Server 2013: Componentes VoIP del servidor front-end'
TOCTitle: Componentes VoIP del servidor front-end
ms:assetid: 310e81a7-da45-47d4-95d0-92837e386502
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg425812(v=OCS.15)
ms:contentKeyID: 48274853
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Componentes VoIP del servidor front-end para Lync Server 2013

 

_**Última modificación del tema:** 2012-10-01_

Los componentes VoIP ubicados en los Servidores front-end son los siguientes:

  - Servicio de conversión

  - Componente de enrutamiento de entrada

  - Componente de enrutamiento de salida

  - Componente de enrutamiento de mensajería unificada de Exchange

  - Componente de enrutamiento entre clústeres

  - [Componente de servidor de mediación en Lync Server 2013](lync-server-2013-mediation-server-component.md)

## Servicio de conversión

El servicio de conversión es el componente de servidor que se encarga de convertir un número marcado al formato E.164 u otro formato, de acuerdo con las reglas de normalización definidas por el administrador. El Servicio de conversión puede convertir a formatos distintos de E.164 si la organización utiliza un sistema de numeración privado o una puerta de enlace o PBX que no admite E.164.

## Componente de enrutamiento de entrada

En gran medida, el componente de enrutamiento de entrada administra las llamadas recibidas según las preferencias especificadas por los usuarios en sus clientes de Telefonía IP empresarial. También facilita las llamadas delegadas y las llamadas simultáneas, si el usuario las configura. Por ejemplo, los usuarios especifican si las llamadas sin contestar se transfieren o simplemente se registran para su notificación. Cuando se habilita la transferencia de llamadas, los usuarios pueden especificar si las llamadas sin contestar se deben transferir a otro número o a un servidor de Mensajería unificada de Exchange configurado para proporcionar contestador automático. El componente de enrutamiento de entrada se instala de forma predeterminada en todos los Servidor Standard Edition y los Servidores front-end.

## Componente de enrutamiento de salida

El componente de enrutamiento de salida redirige las llamadas a destinos PBX o RTC. Aplica reglas de autorización de llamadas, que se definen en la directiva de voz del usuario, a los autores de las llamadas y determina la puerta de enlace RTC óptima para enrutar cada llamada. El componente de enrutamiento de salida se instala de forma predeterminada en todos los Servidor Standard Edition y los Servidores front-end.

La lógica de enrutamiento utilizada por el componente de enrutamiento de salida la configuran en gran medida administradores de red o de telefonía de acuerdo con los requisitos de sus organizaciones.

## Componente de enrutamiento de mensajería unificada de Exchange

El componente de enrutamiento de Mensajería unificada de Exchange administra el enrutamiento entre Lync Server y los servidores que ejecutan la Mensajería unificada de Exchange (UM) para integrar Lync Server con las características de mensajería unificada.

El componente de enrutamiento de Mensajería unificada de Exchange también controla el desvío de correo de voz por la RTC si los servidores de Mensajería unificada de Exchange no están disponibles. Si hay usuarios de Telefonía IP empresarial en sitios de sucursal que no tienen un vínculo WAN resistente a un sitio central, la Aplicación de sucursal con funciones de supervivencia que se implemente en el sitio de sucursal proporciona supervivencia de correo de voz para usuarios de sucursal durante una interrupción de la red WAN. Cuando el vínculo WAN no está disponible, la Aplicación de sucursal con funciones de supervivencia realiza las siguientes acciones:

  - vuelve a enrutar las llamadas por la RTC al servidor de mensajería unificada de Exchange del sitio central

  - proporciona al usuario la posibilidad de recuperar mensajes de correo de voz por la RTC

  - pone en cola las notificaciones de llamada perdida y luego las carga en el servidor de mensajería unificada de Exchange cuando el vínculo WAN se restaura.

Para habilitar el desvío de correo de voz, se recomienda que el administrador de Exchange configure el operador automático (AA) de Mensajería unificada de Exchange para que únicamente acepte mensajes.

Para obtener más información sobre estas características, consulte [Planear la integración de la mensajería unificada de Exchange en Lync Server 2013](lync-server-2013-planning-for-exchange-unified-messaging-integration.md) y [Planear la resistencia de la telefonía IP empresarial en Lync Server 2013](lync-server-2013-planning-for-enterprise-voice-resiliency.md), respectivamente.

## Componente de enrutamiento entre clústeres

El componente de enrutamiento entre clústeres es el responsable del enrutamiento de llamadas al grupo principal del registrador de los destinatarios de las llamadas. Si este no está disponible, el componente enruta la llamada al grupo de reserva del registrador de los destinatarios de las llamadas. Si no se puede tener acceso a los grupos principal y de reserva del registrador de los destinatarios de las llamadas por la red IP, el componente de enrutamiento entre clústeres desvía la llamada por la RTC al número de teléfono del usuario.

## Otros componentes de servidor front-end necesarios para VoIP

Hay otros componentes que residen en el Servidor front-end o el Director que proporcionan compatibilidad esencial para VoIP pero que no son en sí mismos componentes VoIP. Son los siguientes:

  - **Servicios de usuario.** Realiza una búsqueda inversa de número en el número de teléfono de destino de cada llamada entrante y asocia ese número al URI de SIP del usuario de destino. Con esta información, el componente de enrutamiento de entrada distribuye la llamada a los extremos de SIP registrados del usuario. Servicios de usuario es un componente básico de todos los Servidores front-end y los Directores.

  - **Replicador de usuarios.** Extrae números de teléfono de usuarios de Servicios de dominio de Active Directory y los escribe en tablas de la base de datos RTC, donde están disponibles para servicios de usuario y el servidor de libreta de direcciones. Replicador de usuarios es un componente básico de todos los Servidores front-end.

  - **Servidor de libreta de direcciones.** Proporciona información sobre la lista global de direcciones de los Servicios de dominio de Active Directory a los clientes de Lync Server. Asimismo, recupera información de contacto y usuario de la base de datos RTC, escribe la información en los archivos de la libreta de direcciones y, a continuación, almacena los archivos en una carpeta compartida donde los descargan los clientes de Lync. El servidor de libreta de direcciones escribe la información en la base de datos RTCAb, que el servicio de Servicio de consulta web de libreta de direcciones usa para responder a las consultas de búsqueda de usuarios a partir de Microsoft Lync 2010 Mobile. Opcionalmente, normaliza los números de teléfono de los usuarios de empresa que se escriben en la base de datos RTC con el fin de aprovisionar los contactos del usuario en Lync. El servicio de libreta de direcciones se instala de forma predeterminada en todos los Servidores front-end. El servicio de Servicio de consulta web de libreta de direcciones se instala de forma predeterminada con los servicios web en cada Servidores front-end.

