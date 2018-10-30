---
title: Consideraciones acerca de la migración para las reuniones
TOCTitle: Consideraciones acerca de la migración para las reuniones
ms:assetid: a9807d58-99a3-4cff-b4c6-74950d106a2b
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg412800(v=OCS.15)
ms:contentKeyID: 61123867
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Consideraciones acerca de la migración para las reuniones

 

_**Última modificación del tema:** 2014-02-10_

En esta sección se abordan los siguientes temas:

  - Cambios realizados en las reuniones en Microsoft Lync Server 2013

  - Migración de usuarios en función de sus necesidades de conferencias

  - Migración de reuniones existentes y contenido de reuniones

  - Experiencia de los usuarios durante la migración de Lync Server 2010

  - Experiencia de los usuarios durante la migración de Office Communications Server 2007 R2

  - Compatibilidad de Microsoft Lync 2013 con reuniones en versiones de servidor anteriores

## Cambios realizados en las reuniones en Lync Server 2013

Características de **Lync Server 2013.**   Lync Server 2013 proporciona nuevas funciones de conferencia que se ponen a disposición de los usuarios cuando se trasladan sus cuentas a Lync Server 2013 y los usuarios inician sesión en el cliente de Lync 2013. Estas nuevas características se resumen en [Nuevas funciones de conferencia en Lync Server 2013](lync-server-2013-new-conferencing-features.md) y [Novedades para clientes en Lync Server 2013](lync-server-2013-what-s-new-for-clients.md).

**URL de la reunión.**   Como en Lync Server 2010, todas las reuniones que se programan de nuevas en Lync Server 2013 tienen una dirección URL con el prefijo https:// y las reuniones existentes se migran junto con las cuentas de usuario. Sin embargo, Lync Server 2013 no es compatible con la llamada de conferencia de Office Communications Server 2007 R2 (conf:// URL prefix) ni con la conferencia web (meet:// URL prefix). Encontrará más información en “Migración de reuniones desde Office Communications Server 2007 R2”, más adelante en este tema.

**Compatibilidad con clientes.**   A diferencia de Lync Server 2010, Lync Server 2013 no es compatible con los clientes de Office Communicator para las conferencias. No se puede utilizar los clientes siguientes para unirse a reuniones programadas con Complemento para conferencia en línea para Lync 2013:

  - Office Communicator 2007 R2

  - Operador de Microsoft Office Communications Server 2007 R2

  - Office Communicator 2007

  - Office Live Meeting 2007

Durante la migración, los usuarios de Office Communicator 2007 R2 deben usar Lync Web App 2013 para unirse a reuniones de Lync Server 2013 hasta que se actualicen sus clientes. Observe que los usuarios de Office Communicator 2007 R2 pueden continuar usando su cliente actual en Lync Server 2013 para las características de presencia y de mensajería instantánea, pero no se admiten las características de conferencia.


## Migración de usuarios en función de sus necesidades de conferencias

**Organizadores de reuniones frecuentes.**   Considere la posibilidad de migrar a organizadores de reuniones frecuentes en las primeras fases del proceso para que puedan sacar partido de las nuevas características de Lync Server 2013 y Lync 2013, descritas en [Nuevas funciones de conferencia en Lync Server 2013](lync-server-2013-new-conferencing-features.md) y [Novedades para clientes en Lync Server 2013](lync-server-2013-what-s-new-for-clients.md).

**Usuarios de Live Meeting.**   Si la migración se realiza desde Office Communications Server 2007 R2 y tiene usuarios que necesitan las funciones de conferencia web específicas de Live Meeting (concretamente, la compatibilidad con reuniones de gran tamaño y salas de descanso), tiene las siguientes opciones:

  - Recomendar a los organizadores que utilicen el servicio Live Meeting, si está disponible en su empresa.

  - Dejar a los organizadores hospedados en la versión anterior de Office Communications Server para que puedan continuar programando conferencias web de Live Meeting basadas en el servidor.

## Migración de reuniones existentes y contenido de reuniones

## Migración de reuniones desde Lync Server 2010

Cuando traslade a un usuario de Lync Server 2010 a Lync Server 2013, se trasladará también la información siguiente con la cuenta del usuario:

  - Reuniones ya programadas por el usuario. Incluye los directorios y los datos de conferencia.

  - Número de identificación personal (PIN) del usuario. El PIN actual del usuario seguirá funcionando hasta que caduque o hasta que el usuario solicite un PIN nuevo.

Por el contrario, no se pasa al nuevo servidor la información de la cuenta del usuario siguiente:

  - Contenido de las reuniones, como, por ejemplo, presentaciones de PowerPoint, el contenido de las pizarras y los datos de sondeos

Para mover el contenido que se ha compartido durante las reuniones, utilice el parámetro MoveMeetingContent del cmdlet Move-CsUser. Si desea información sobre el uso de este cmdlet, consulte [Move-CsUser](https://docs.microsoft.com/en-us/powershell/module/skype/Move-CsUser) en la documentación de cmdlets de Lync Server 2013.

## Migración de reuniones desde Office Communications Server 2007 R2

Las reuniones de Office Communications Server 2007 R2 pueden ser llamadas de conferencia (conf:// URL prefix) o conferencias web (meet:// URL prefix). Lync Server 2013 no es compatible con estas conferencias conf:// y meet:// anteriores y no se migran junto con la cuenta de usuario. Después de la migración, tendrá que pedir a los usuarios que actualicen los enlaces de las reuniones en línea que hayan programado. Pueden hacerlo después de instalar el cliente de Lync 2013 abriendo una invitación a una reunión programada (con lo que se actualiza la URL de la reunión) y reenviando la invitación a los participantes.

## Experiencia de usuario durante la migración de Lync Server 2010

En esta sección se resume la experiencia de conferencias de los usuarios cuando migran desde Lync 2010. Si desea información detallada sobre cómo pueden los clientes de Lync Server 2013 coexistir e interactuar con versiones de cliente y servidor anteriores, consulte [Interoperabilidad de clientes en Lync 2013](lync-server-2013-client-interoperability-in-lync-2013.md).

## Cómo unirse a reuniones de Lync Server 2010 con un cliente Lync 2013

Durante la migración desde Lync Server 2010, puede haber un período de coexistencia cuando los usuarios se unen a las reuniones de Lync Server 2010 con un cliente de Lync 2013. Estos usuarios tienen acceso a las características de cliente de Lync 2013, con las siguientes excepciones:

  - En las opciones de administración **Participantes**, a las que puede acceder seleccionando el icono de contactos de la ventana de reuniones, la opción **No aceptar reuniones de MI** no funciona.

  - La vista Galería no funciona en las conferencias de vídeo. El usuario solo ve al hablante activo, en lugar de ver a todos los hablantes. En la lista de opciones **Seleccionar un diseño**, **Vista de galería** no se encuentra disponible.

  - La lista de participantes se muestra de manera predeterminada en las conferencias de vídeo.

  - Al hacer clic con el botón secundario en un usuario de la lista de participantes, las opciones de administración de participantes **Bloquear el foco de vídeo** y **Anclar a galería** no se encuentran disponibles.

## Experiencia de usuario durante la migración de Office Communications Server 2007 R2

En esta sección se resume la experiencia de los usuarios en las conferencias cuando migran desde Office Communications Server 2007 R2, tanto antes, como después de instalar Lync 2013. Si desea más información sobre cómo pueden los clientes de Lync Server 2013 coexistir e interactuar con versiones de cliente y servidor anteriores, consulte [Interoperabilidad de clientes en Lync 2013](lync-server-2013-client-interoperability-in-lync-2013.md).

## Después de migrar la cuenta de usuario, antes de instalar Lync 2013

Después de migrar un usuario al servidor de Lync Server 2013, pero antes de instalar los nuevos clientes, los usuarios de Office Communicator 2007 R2 pueden continuar usando su cliente existente en Lync Server 2013 para las características de presencia y mensajería instantánea, pero no para las de conferencia.

## Después de migrar la cuenta de usuario, después de instalar Lync 2013

Cuando un usuario migrado instala Lync 2013, también se instala el complemento de reuniones en línea para Lync 2013, con las siguientes consecuencias:

  - Todas las reuniones que se programen a partir de ese momento utilizarán el nuevo formato de reunión, que utiliza una dirección https://, en lugar de la dirección meet:// heredada de Live Meeting.

  - En una implementación administrada por el departamento de TI de Lync 2013, el administrador tiene la opción de desinstalar el complemento de conferencias para Microsoft Office Outlook, que se utiliza para programar reuniones basadas en servicios y en servidores de Live Meeting. Sin embargo, puede tener usuarios que necesiten continuar programando reuniones de servicios de Live Meeting. En ese caso, puede permitir la coexistencia de ambos complementos.

## Reuniones con organizaciones federadas que utilizan clientes anteriores

Los usuarios de organizaciones federadas que utilizan Microsoft Office Communicator 2007 no se pueden unir a reuniones de Lync Server 2013 en su organización si esas reuniones han sido bloqueadas por el organizador. Tendrá que volver a programarlas en Lync Server 2013 para que cuando los participantes federados se unan a la reunión usando la nueva dirección URL https://, puedan usar Lync Web App.

