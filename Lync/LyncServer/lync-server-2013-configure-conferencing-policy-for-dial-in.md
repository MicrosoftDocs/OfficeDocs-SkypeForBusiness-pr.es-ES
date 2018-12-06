---
title: '     Lync Server 2013: Configurar directiva de conferencias para acceso telefónico local'
TOCTitle: Configurar la directiva de conferencias para el acceso telefónico local
ms:assetid: 9bf926d6-0248-4352-98c3-9c5a333debbc
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg398810(v=OCS.15)
ms:contentKeyID: 48276137
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configurar la directiva de conferencias para el acceso telefónico local en Lync Server 2013

 

_**Última modificación del tema:** 2014-03-21_

Las directivas de conferencias son una opción de cuenta de usuario que especifica la experiencia de conferencia de los participantes. Puede crear directivas de conferencia cuyo ámbito sea de sitio o de usuario. La configuración de directiva de conferencias abarca muchos aspectos de la programación de conferencias y de la participación en ellas. Varias configuraciones de directiva de conferencias admiten las conferencias de acceso telefónico local para los participantes. Cuando configure la característica de conferencia de acceso telefónico local, debe comprobar que estos campos estén definidos de la forma apropiada para su organización, y modificarlos según sea necesario.

Compruebe los campos siguientes en la directiva de conferencias:

  - **Permitir a los participantes invitar a usuarios anónimos**    Esta opción permite a los organizadores de reuniones invitar a participantes anónimos (es decir, no autenticados) a reuniones. No es obligatoria para las conferencias de acceso telefónico local. Esta opción está seleccionada de forma predeterminada en la directiva de conferencias global predeterminada.

  - **Habilitar conferencia de acceso telefónico local por RTC**    Esta opción permite a los usuarios participar en la parte de audio de una conferencia mediante acceso telefónico desde la RTC. Esta opción es obligatoria para las conferencias de acceso telefónico local. Esta opción está seleccionada de forma predeterminada en la directiva de conferencias global predeterminada.

  - **Permitir acceso telefónico a los participantes anónimos**    Esta opción permite a los usuarios anónimos que ya se hayan unido a la reunión el acceso telefónico a un número de teléfono para unirse a la parte de audio de la conferencia. No es obligatoria para las conferencias de acceso telefónico local. Esta opción no está seleccionada de forma predeterminada en la directiva de conferencias global predeterminada.

  - **Permitir acceso telefónico a los participantes no habilitados para Telefonía IP empresarial** Esta opción permite a los organizadores y participantes en reuniones que no están habilitados para Telefonía IP empresarial el acceso telefónico a un número de teléfono para unirse a la parte de audio de la conferencia. La llamada de salida se autoriza según la directiva de voz asignada por el organizador. Esta opción no está seleccionada de forma predeterminada en la directiva de conferencias global predeterminada. El valor predeterminado está deshabilitado.
    

    > [!NOTE]
    > Para habilitar esta capacidad, un organizador de reuniones no habilitado para Telefonía IP empresarial deberá tener asignada una directiva de voz apropiada para autorizar el acceso telefónico desde una conferencia organizada por ese usuario. Puede asignar una directiva de voz a un usuario no habilitado para Telefonía IP empresarial desde el Shell de administración de Lync Server. Si el usuario no tiene asignada explícitamente una directiva de voz, se utiliza la directiva de voz del sitio para autorizar la solicitud de acceso telefónico. Si no hay ninguna directiva de voz del sitio, se usará la directiva global.&nbsp;&nbsp;



El procedimiento descrito en esta sección explica cómo modificar la directiva de conferencia. Para obtener más información sobre cómo configurar todas las opciones que definen la experiencia del participante en la directiva de conferencia predeterminada, consulte [Creación o modificación de un conjunto de opciones de configuración de reuniones en Lync Server 2013](lync-server-2013-create-or-modify-a-collection-of-meeting-configuration-settings.md). Para obtener más información sobre cómo crear una directiva de conferencia para un usuario específico o un grupo de usuarios, consulte [Creación o modificación de una directiva de conferencia en Lync Server 2013](lync-server-2013-create-or-modify-a-conferencing-policy.md). Para obtener una lista de las configuraciones de directivas de conferencias disponibles, consulte [Referencia de configuración de directivas de conferencias en Lync Server 2013](lync-server-2013-conferencing-policy-settings-reference.md).

## Para modificar la directiva de conferencias para el acceso telefónico

1.  Inicie sesión en el equipo como miembro del grupo RTCUniversalServerAdmins o como miembro del rol **Cs-ServerAdministrator** o **CsAdministrator** .

2.  Abra una ventana del explorador y después introduzca la dirección URL de administración para abrir el panel de control de Lync Server. Para más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Abrir las herramientas administrativas de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Conferencia** .

4.  En la pestaña **Directiva de conferencias** , haga doble clic en el nombre de una directiva de conferencias para abrir el cuadro de diálogo **Editar directiva de conferencia** .

5.  Compruebe que los campos de conferencia de acceso telefónico local sean adecuados para su organización y modifique la configuración si es necesario.

6.  Haga clic en **Confirmar** .

