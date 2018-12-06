---
title: 'Lync Server 2013: Habilitar a los usuarios para la telefonía IP empresarial'
TOCTitle: Habilitar a los usuarios para la telefonía IP empresarial
ms:assetid: f252b23b-9641-4160-aa81-bf06dc2eced3
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg413011(v=OCS.15)
ms:contentKeyID: 48277136
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Habilitar a los usuarios para la telefonía IP empresarial en Lync Server 2013

 

_**Última modificación del tema:** 2012-11-01_

Después de instalar los archivos de uno o varios servidores de mediación, configurar el enrutamiento de llamadas salientes y, si se desea, implementar una o varias funciones avanzadas de Telefonía IP empresarial, siga los siguientes procedimientos para habilitar la realización de llamadas de un usuario con Telefonía IP empresarial:


> [!NOTE]
> De los siguientes procedimientos, solo el primero se puede realizar con Panel de control de Lync Server. Para el resto de los procedimientos, solamente puede usar Shell de administración de Lync Server.



  - Habilitar la cuenta de usuario para Telefonía IP empresarial.

  - (Opcional) Asignar a la cuenta de usuario una directiva de voz específica para el usuario.

  - (Opcional) Asignar a la cuenta de usuario un plan de marcado específico para el usuario.

## Habilitar una cuenta de usuario para Telefonía IP empresarial.

1.  Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y después introduzca la dirección URL de administración para abrir el panel de control de Lync Server. Para más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Abrir las herramientas administrativas de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Usuarios**.

4.  En el cuadro **Buscar usuarios**, escriba la primera parte del nombre para mostrar, el nombre, los apellidos, el nombre de la cuenta del Administrador de cuentas de seguridad (SAM), la dirección SIP o el identificador uniforme de recursos (URI) de línea de la cuenta de usuario que desee habilitar y, a continuación, haga clic en **Buscar**.

5.  En la tabla, haga clic en la cuenta de usuario que desee habilitar para Telefonía IP empresarial.

6.  En el menú **Editar**, haga clic en **Mostrar detalles**.

7.  En la página **Editar usuario de Lync Server**, en **Telefonía**, haga clic en **Telefonía IP empresarial**.

8.  Haga clic en **URI de línea** y, a continuación, escriba un número de teléfono exclusivo y normalizado (por ejemplo, tel:+14255550200).

9.  Haga clic en**Confirmar**.

Para terminar de habilitar un usuario para Telefonía IP empresarial, compruebe que al usuario se le ha asignado una directiva de voz y un plan de marcado, ya sea global (asignado de forma predeterminada) o específico para el usuario.

De manera predeterminada, a todos los usuarios se les asigna una directiva de voz global y un plan de marcado. Si ya hubiera una directiva de voz o un plan de marcado a nivel de sitio para el sitio en el que se hospeda la cuenta de usuario, se aplicarán automáticamente al usuario. Para aplicar una directiva de voz o plan de marcado por usuario a un usuario, deberá ejecutar los cmdlets **Grant-CsVoicePolicy** y **Grant-CsDialPlan**. Para más información, consulte la documentación [Shell de administración de Lync Server](lync-server-2013-lync-server-management-shell.md).

## Asignación de directivas de voz

A todas las cuentas de usuario habilitadas para Telefonía IP empresarial se asignan automáticamente directivas de voz a nivel global o de sitio. También puede crear directivas de voz aplicables a usuarios o grupos específicos. Estas directivas por usuario deben estar explícitamente asignadas a los usuarios o grupos. Si desea utilizar la directiva de voz global o del sitio a todos los usuarios habilitados para Telefonía IP empresarial, puede omitir esta sección y continuar por Asignación de planes de marcado más adelante en este tema.

## Para asignar una directiva de voz específica del usuario

1.  Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y, después, en **Shell de administración de Lync Server**.

3.  Para asignar una directiva de voz de usuario existente a un usuario, ejecute lo siguiente en el símbolo del sistema:
    
        Grant-CsVoicePolicy -Identity <UserIdParameter> -PolicyName <String>
    
    Por ejemplo:
    
        Grant-CsVoicePolicy -Identity "Bob Kelly" -PolicyName VoicePolicyJapan
    
    En este ejemplo, al usuario con nombre para mostrar Carlos Tudela se le asigna la directiva de voz con el nombre **VoicePolicyJapan**.

Para ver los detalles acerca de cómo asignar una directiva de voz específica del usuario o ejecutar el cmdlet **Grant-CsVoicePolicy**, consulte la documentación de [Shell de administración de Lync Server](lync-server-2013-lync-server-management-shell.md).

## Asignación de planes de marcado

Para completar la configuración de cuentas de usuario para los usuarios de la Telefonía IP empresarial o para los usuarios de conferencias de acceso telefónico local, asigne un plan de marcado. Las cuentas de usuario emplearán automáticamente el plan de marcado global o, si existe, el plan de marcado del sitio, en los casos en los que no se asigne explícitamente un plan de marcado creado particularmente para el usuario. Si desea utilizar el plan de marcado global o del sitio para todos los usuarios habilitados para Telefonía IP empresarial, puede omitir esta sección.

## Para asignar un plan de marcado

1.  Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y, después, en **Shell de administración de Lync Server**.

3.  Para asignar un plan de marcado específico del usuario, ejecute lo siguiente en el símbolo del sistema:
    
        Grant-CsDialPlan -Identity <UserIdParameter> -PolicyName <String>
    
    Por ejemplo:
    
        Grant-CsDialPlan -Identity "Bob Kelly" -PolicyName DialPlanJapan
    
    En este ejemplo, al usuario con nombre para mostrar Carlos Tudela se le asigna el plan de marcado específico del usuario con el nombre **DialPlanJapan**.

Para ver los detalles de la asignación de un plan de marcado de usuario o de la ejecución del cmdlet **Grant-CsDialPlan**, consulte la documentación de [Shell de administración de Lync Server](lync-server-2013-lync-server-management-shell.md).

## Vea también

#### Tareas

[Deshabilitar a un usuario para Enterprise Voice en Lync Server 2013](lync-server-2013-disable-a-user-for-enterprise-voice.md)

