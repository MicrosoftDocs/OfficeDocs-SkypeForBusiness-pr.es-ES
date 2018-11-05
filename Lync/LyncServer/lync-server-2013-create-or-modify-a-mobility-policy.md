---
title: Creación o modificación de una directiva de movilidad
TOCTitle: Creación o modificación de una directiva de movilidad
ms:assetid: fc2dfea0-2215-440d-9f4b-7c985da29211
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ721946(v=OCS.15)
ms:contentKeyID: 49889830
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Creación o modificación de una directiva de movilidad

 

_**Última modificación del tema:** 2013-02-23_

Puede crear o modificar directivas de movilidad para permitir a los usuarios de móviles utilizar los dispositivos móviles compatibles para las funcionalidades de Lync, como la mensajería instantánea (MI), presencia y contactos. Puede crear o modificar directivas de movilidad en Panel de control de Lync Server 2013 o Shell de administración de Lync Server 2013

## Para crear una directiva de movilidad en Panel de control de Lync Server

1.  Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y después introduzca la dirección URL de administración para abrir el panel de control de Lync Server. Para más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Abrir las herramientas administrativas de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Clientes** y, a continuación, en el botón de navegación **Directiva de movilidad**.

4.  En la página **Directiva de movilidad**, haga clic en **Nueva** y siga uno de los procedimientos siguientes:
    
    1.  Para crear una directiva de movilidad de sitio, haga clic en **Directiva de sitio**, haga clic en un sitio y en **Aceptar**. Reviste la configuración predeterminada y realice los cambios que desee.
    
    2.  Para crear una directiva de movilidad, haga clic en **Directiva de usuario**, escriba un nombre, revise la configuración predeterminada y realice los cambios que desee.

5.  Haga clic en **Confirmar** .

## Para modificar una directiva de movilidad en Panel de control de Lync Server

1.  Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y después introduzca la dirección URL de administración para abrir el panel de control de Lync Server. Para más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Abrir las herramientas administrativas de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Clientes** y, a continuación, en el botón de navegación **Directiva de movilidad**.

4.  En la página **Directiva de movilidad**, haga clic en una de las directivas de movilidad existentes.

5.  En el menú **Editar** , haga clic en **Mostrar detalles** .

6.  Edite cualquiera de las opciones.

7.  Haga clic en **Confirmar** .

## Eliminación de directivas de acceso externo usando los cmdlets de Windows PowerShell

Las directivas de movilidad también se pueden crear (en el ámbito de sitio y en el de usuario) usando Windows PowerShell y el cmdlet **New-CsMobilityPolicy**. Además, puede utilizar el cmdlet **Set-CsMobilityPolicy** para modificar cualquiera de las directivas existentes, incluida la directiva global. Estos cmdlets se pueden ejecutar desde Shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell. Para más información sobre el uso de una conexión remota de Windows PowerShell a Lync Server, consulte el artículo del blog sobre Windows PowerShell de Lync Server "Inicio rápido: Administración de Microsoft Lync Server 2010 con PowerShell remoto" en [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

## Creación de una directiva de movilidad en el ámbito de sitio

  - Este comando crea una directiva de movilidad nueva para el sitio Redmond:
    
        New-CsMobilityPolicy -Identity "site:Redmond"
    
    Como no se han especificado parámetros (aparte del parámetro obligatorio Identity) en el comando anterior, las directivas utilizarán los valores predeterminados en todas sus propiedades.

## Creación de una directiva de movilidad en el ámbito de usuario

  - Para crear una directiva de movilidad en el ámbito de usuario, especifique una identidad única para la directiva:
    
        New-CsMobilityPolicy -Identity "RedmondMobilityPolicy"

## Cambio de un valor de propiedad único cuando se crea una directiva de movilidad

  - Para crear directivas que utilicen diferentes valores de propiedad, incluya el parámetro adecuado y el valor de parámetro. Por ejemplo, este comando crea una directiva de movilidad que deshabilita las llamadas vía trabajo:
    
        New-CsMobilityPolicy -Identity "site:Redmond" -EnableOutsideVoice $False

## Cambio de varios valores de propiedades al crear una directiva de movilidad

  - Se pueden modificar varios valores de propiedad incluyendo varios parámetros. Por ejemplo, este comando crea una directiva que deshabilita tanto la movilidad como la llamada vía trabajo:
    
        New-CsMobilityPolicy "site:Redmond" -EnableMobility $False -EnableOutsideVoice $False

Para obtener más información, consulte el tema de ayuda relativo a los cmdlets [New-CsMobilityPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsMobilityPolicy) y [Set-CsMobilityPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsMobilityPolicy).

## Vea también

#### Tareas

[Configuración de la directiva de movilidad en Lync Server 2013](lync-server-2013-configuring-mobility-policy.md)

