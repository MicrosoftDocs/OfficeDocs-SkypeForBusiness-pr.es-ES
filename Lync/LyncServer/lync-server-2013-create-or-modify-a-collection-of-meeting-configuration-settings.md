---
title: Crear o modificar una colección de valores de configuración de reuniones
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a collection of meeting configuration settings
ms:assetid: ce6773c1-a0d5-4405-8e32-33a6f3a46a1a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721889(v=OCS.15)
ms:contentKeyID: 49733822
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0a5f80066a68b45e062a351478bea93a5c2e8fd0
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763342"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-collection-of-meeting-configuration-settings-in-lync-server-2013"></a>Crear o modificar una colección de opciones de configuración de reuniones en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-23_

Puede usar la configuración de la página Configuración de la reunión para definir diversas características de la experiencia de unirse a la reunión. De forma predeterminada, la configuración global define la experiencia de la combinación. También puede crear la configuración de combinación de reuniones en el nivel de sitio y en el nivel de grupo. Si crea una configuración a nivel de grupo, esa configuración se aplicará a todas las reuniones que ese grupo de servidores hospeda. Si no crea ninguna configuración a nivel de grupo, se aplicará la configuración a nivel de sitio, si existe. Si no define la configuración a nivel de sitio, se aplicará la configuración global a todas las reuniones.

<div>

## <a name="to-create-new-meeting-join-settings"></a>Para crear una nueva configuración de unirse a la reunión

1.  Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [abrir las herramientas administrativas 2013 de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Conferencia** y, a continuación, en **configuración de reunión**.

4.  En la página **Configuración de reunión**, haga clic en **Nueva** y después realice una de las siguientes acciones:
    
      - Para crear una directiva de nivel de sitio, haga clic en **Configuración de sitio**. En el campo de búsqueda **Seleccionar un sitio**, escriba el nombre, o parte del nombre, del sitio para el que desee definir la configuración de participación en reuniones. En la lista de sitios resultante, haga clic en el sitio que desee y después en **Aceptar**.
    
      - Para crear una directiva de nivel de grupo de servidores, haga clic en **Configuración del grupo de servidores**. En el campo de búsqueda **Seleccionar un servicio**, escriba el nombre, o parte del nombre, del servicio del grupo de servidores para el que desee definir la configuración de participación en reuniones. En la lista de servicios resultante, haga clic en el grupo de servidores que desee y después en **Aceptar**.

5.  Para redirigir a los participantes que realizaron la llamada desde una red telefónica conmutada (RTC) a través de la sala de espera, desactive la casilla **Los autores de llamadas RTC no pasan por la sala de espera**. Normalmente, los participantes que efectúen la llamada desde la RTC obtendrán acceso directamente a la reunión.

6.  Para configurar quién puede ser moderador en una reunión, en **Designar como moderador**, lleve a cabo uno de los procedimientos siguientes:
    
      - Para que solo sea moderador el organizador, haga clic en **Ninguno**.
    
      - Para que solo sean moderadores los participantes que pertenezcan a la organización, haga clic en **Compañía**. Esta es la configuración que se aplica normalmente.
    
      - Para que cualquier participante sea moderador, haga clic en **Todos**.

7.  Para que el moderador pueda seleccionar un tipo de conferencia cuando se programe una reunión, desactive la casilla **Tipo de conferencia asignada de forma predeterminada**. Normalmente, el tipo de conferencia se asigna automáticamente.

8.  Para evitar que se admitan automáticamente a usuarios anónimos (sin autenticar), desactive la casilla **Admitir usuarios anónimos de forma predeterminada**. Normalmente, los usuarios anónimos se admiten automáticamente en las reuniones.

9.  Para personalizar la invitación a la reunión que se envía a los participantes, haga lo siguiente. Recuerde que la longitud máxima de las direcciones URL y el texto de pie de página personalizado es de 1 KB. Salvo en el caso de la **Dirección URL de la Ayuda**, si no especifica un valor para las personalizaciones, no se incluirán en la reunión. Si no incluye una dirección URL de ayuda personalizada, la dirección URL de la ayuda predeterminada para Lync se mostrará en la invitación.
    
      - Para personalizar el logotipo que aparece en la invitación a la reunión, en **dirección URL del logotipo** introduzca la ubicación del logotipo.
        
        <div>
        

        > [!NOTE]
        > El logotipo debe ser una imagen GIF o JPG con un tamaño de 188 por 30 píxeles.

        
        </div>
    
      - Para personalizar el texto de ayuda que aparece en la invitación a la reunión, en la **Dirección URL de la Ayuda**, introduzca la ubicación del texto de ayuda.
    
      - Para personalizar el texto legal que aparece en la invitación de la reunión, en **Dirección URL del texto legal**, introduzca la ubicación del texto legal.
    
      - Para personalizar el texto del pie de página que aparece en la invitación a la reunión, en **Texto de pie de página personalizado**, escriba el texto.

10. Haga clic en **Confirmar**.

</div>

<div>

## <a name="to-modify-an-existing-collection-of-meeting-configurations"></a>Para modificar una colección de configuraciones de reunión existente

1.  Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [abrir las herramientas administrativas 2013 de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Conferencia** y, a continuación, en **configuración de reunión**.

4.  En la lista de configuraciones de la reunión, haga clic en la configuración que desee cambiar, luego, haga clic en **Editar** y, por último, en **Mostrar detalles**.

5.  En **Editar configuración de reunión**, modifique cualquiera de las opciones de configuración, excepto el nombre de la configuración, que no se puede modificar.

6.  Haga clic en **Confirmar**.

</div>

<div>

## <a name="creating-new-meeting-configuration-settings-by-using-windows-powershell-cmdlets"></a>Crear una nueva configuración de reunión mediante cmdlets de Windows PowerShell

Se pueden crear parámetros de configuración de reunión (solo en el ámbito del sitio) mediante Windows PowerShell y el cmdlet New-CsMeetingConfiguration. Este cmdlet se puede ejecutar desde el shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell. Para obtener más información sobre cómo usar Windows PowerShell remoto para conectarse a Lync Server, consulte el artículo del blog de Lync Server de Windows PowerShell "Inicio rápido: administrar Microsoft Lync Server [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)2010 mediante PowerShell remoto" en.

<div>

## <a name="to-create-meeting-configuration-settings-that-use-the-default-values"></a>Para crear una configuración de reunión que use los valores predeterminados

  - Este comando crea un nuevo conjunto de opciones de configuración de reunión para el sitio de Redmond:
    
        New-CsMeetingConfiguration -Identity "site:Redmond"
    
    Como no se especificó ningún parámetro (salvo el parámetro de identidad obligatorio) en el comando anterior, la configuración de reunión nueva usará los valores habituales para todas sus propiedades.

</div>

<div>

## <a name="to-change-a-property-value-when-creating-meeting-configuration-settings"></a>Para cambiar el valor de una propiedad al crear una configuración de reunión

  - Para crear configuraciones que usen valores de propiedad diferentes, solo tiene que incluir el parámetro y el valor de parámetro adecuado. Por ejemplo, para crear una colección de configuraciones de reunión que admitan siempre a todos los participantes de una reunión como moderadores, use un comando como este:
    
        New-CsMeetingConfiguration -Identity "site:Redmond" -DesignateAsPresenter "Everyone"

</div>

<div>

## <a name="to-change-multiple-property-values-when-creating-meeting-configuration-settings"></a>Para cambiar los valores de varias propiedades al crear una configuración de reunión

  - Puede incluir varios parámetros para modificar varios valores de propiedad. Por ejemplo, este comando admite a todos los participantes en una reunión como moderador y también obliga a los usuarios de la RTC a esperar en la sala de espera hasta que se admitan formalmente en la reunión:
    
        New-CsMeetingConfiguration -Identity "site:Redmond" -DesignateAsPresenter "Everyone" -PSTNUCallersBypassLobby $True

</div>

Para obtener más información, vea el tema de ayuda sobre el cmdlet [New-CsMeetingConfiguration](https://technet.microsoft.com/en-us/library/Gg398065(v=OCS.15)) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

