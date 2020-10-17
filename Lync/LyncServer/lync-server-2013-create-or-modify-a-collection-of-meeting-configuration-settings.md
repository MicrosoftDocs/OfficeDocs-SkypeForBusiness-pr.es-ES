---
title: Crear o modificar una colección de opciones de configuración de reuniones
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
ms.openlocfilehash: fb7f5df9a734fc248afbe0bf21739b95ecfba285
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48516907"
---
# <a name="create-or-modify-a-collection-of-meeting-configuration-settings-in-lync-server-2013"></a>Crear o modificar una colección de opciones de configuración de reuniones en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-23_

Use la configuración de la página Configuración de reunión para definir diversas características de la experiencia de participar en una reunión. Normalmente, la participación se rige por la configuración global. También puede crear configuraciones de participación en reuniones en el nivel de sitio y en el nivel de grupo de servidores. Si crea una configuración en el nivel de grupo de servidores, esa configuración se aplicará a todas las reuniones que ese grupo de servidores hospeda. Si no crea ninguna configuración en el nivel de grupo de servidores, se aplicará la configuración del nivel de sitio, si existe. Si no define la configuración en el nivel de sitio, se aplicará la configuración global a todas las reuniones.

<div>

## <a name="to-create-new-meeting-join-settings"></a>Para crear nuevas configuraciones de participación en reuniones

1.  Desde una cuenta de usuario asignada al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Conferencia** y después en **Configuración de reunión**.

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
    
      - Para personalizar el logotipo que aparece en la invitación de la reunión, en **Dirección URL del logotipo**, especifique la ubicación del logotipo.
        
        <div>
        

        > [!NOTE]
        > El logotipo debe ser una imagen GIF o JPG con un tamaño de 188 por 30 píxeles.

        
        </div>
    
      - Para personalizar el texto de ayuda que aparece en la invitación a la reunión, en la **Dirección URL de la Ayuda**, especifique la ubicación del texto de ayuda.
    
      - Para personalizar el texto legal que aparece en la invitación de la reunión, en **Dirección URL del texto legal**, especifique la ubicación del logotipo.
    
      - Para personalizar el texto del pie de página que aparece en la invitación a la reunión, en **Texto de pie de página personalizado**, escriba el texto.

10. Haga clic en **Confirmar**.

</div>

<div>

## <a name="to-modify-an-existing-collection-of-meeting-configurations"></a>Para modificar una colección de configuraciones de reunión existente

1.  Desde una cuenta de usuario asignada al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Conferencia** y después en **Configuración de reunión**.

4.  En la lista de configuraciones de reunión, haga clic en la configuración que desee cambiar, haga clic en **Editar**y, a continuación, haga clic en **Mostrar detalles**.

5.  En **Editar configuración de reunión**, modifique cualquiera de las configuraciones de participación en reuniones, excepto el nombre, que no se puede modificar.


6.  Haga clic en **Confirmar**.

</div>

<div>

## <a name="creating-new-meeting-configuration-settings-by-using-windows-powershell-cmdlets"></a>Crear nuevas opciones de configuración de reuniones con los cmdlets de Windows PowerShell

Se pueden crear opciones de configuración de reunión (solo en el ámbito del sitio) mediante Windows PowerShell y el cmdlet New-CsMeetingConfiguration. Este cmdlet se puede ejecutar desde el shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell. Para obtener información detallada sobre cómo usar Windows PowerShell remoto para conectarse a Lync Server, consulte el artículo del blog de Lync Server Windows PowerShell "Inicio rápido: administración de Microsoft Lync Server 2010 mediante PowerShell remoto" en [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .

<div>

## <a name="to-create-meeting-configuration-settings-that-use-the-default-values"></a>Para crear opciones de configuración de reunión que usen los valores predeterminados

  - Este comando crea un conjunto de configuraciones de reunión nuevo para el sitio de Redmond:
    
        New-CsMeetingConfiguration -Identity "site:Redmond"
    
    Como no se especificó ningún parámetro (salvo el parámetro de identidad obligatorio) en el comando anterior, la configuración de reunión nueva usará los valores habituales para todas sus propiedades.

</div>

<div>

## <a name="to-change-a-property-value-when-creating-meeting-configuration-settings"></a>Para cambiar el valor de una propiedad al crear una configuración de reunión

  - Para crear configuraciones que usen valores de propiedad diferentes, solo tiene que incluir el parámetro y el valor de parámetro adecuado. Por ejemplo, para crear una colección de configuraciones de reunión que admitan siempre a todos los participantes de una reunión como moderadores, use un comando como este:
    
        New-CsMeetingConfiguration -Identity "site:Redmond" -DesignateAsPresenter "Everyone"

</div>

<div>

## <a name="to-change-multiple-property-values-when-creating-meeting-configuration-settings"></a>Para cambiar varios valores de propiedad al crear opciones de configuración de reunión

  - Puede cambiar varios valores de propiedad incluyendo varios parámetros. Por ejemplo, este comando admite a todos los participantes de la reunión como moderadores y también obliga a los usuarios de RTC a permanecer en la sala de espera hasta que se les admita formalmente a la reunión:
    
        New-CsMeetingConfiguration -Identity "site:Redmond" -DesignateAsPresenter "Everyone" -PSTNUCallersBypassLobby $True

</div>

Para obtener más información, consulte el tema de ayuda del cmdlet [New-CsMeetingConfiguration](https://technet.microsoft.com/library/Gg398065(v=OCS.15)) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

