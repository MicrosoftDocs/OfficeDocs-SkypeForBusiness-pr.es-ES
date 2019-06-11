---
title: 'Lync Server 2013: crear o modificar una regla de traducción de forma manual'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create or modify a translation rule manually
ms:assetid: 049d1db3-af58-48c5-be89-52e1d068a4bd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398099(v=OCS.15)
ms:contentKeyID: 48183276
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 445b17b5a878e066ed0a77c725ae035101d57469
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34835781"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-translation-rule-manually-in-lync-server-2013"></a>Crear o modificar una regla de traducción de forma manual en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-08-06_

Siga estos pasos si desea definir una regla de traducción escribiendo una expresión regular para el patrón y la regla de traducción coincidentes. También puede introducir un conjunto de valores en la herramienta **generar una regla de traducción** y habilitar el panel de control de Lync Server para generar la regla de traducción y el patrón de coincidencia correspondiente. Para obtener más información, consulte [crear o modificar una regla de traducción con la herramienta generar una regla de traducción de Lync Server 2013](lync-server-2013-create-or-modify-a-translation-rule-by-using-the-build-a-translation-rule-tool.md).

<div>

## <a name="to-define-a-translation-rule-manually"></a>Para definir una regla de conversión de forma manual

1.  Inicie sesión en el equipo como miembro del grupo RTCUniversalServerAdmins o como miembro del rol CsVoiceAdministrator, CsServerAdministrator o CsAdministrator. Para obtener más información, consulte [permisos de configuración de delegación en Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [abrir las herramientas administrativas 2013 de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Para empezar a definir una regla de traducción, siga los pasos que se indican en [configurar un tronco con la omisión de medios en Lync server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md) hasta el paso 10 o [configurar un tronco sin evitar los medios en Lync Server 2013](lync-server-2013-configure-a-trunk-without-media-bypass.md) a paso 9.

4.  En el campo **Nombre** de las páginas **Nueva regla de conversión** o **Editar regla de conversión**, escriba un nombre que describa el patrón de número de objeto de la conversión.

5.  (Opcional) En **Descripción**, escriba una descripción de la regla de conversión, por ejemplo, **US International long-distance dialing**.

6.  Haga clic en **Editar** en la parte inferior de la sección **Crear una regla de conversión**.

7.  Especifique lo siguiente en **Escribir una expresión regular**:
    
      - En **Hacer coincidir este patrón**, especifique el patrón que se usará para hacer coincidir los números objeto de la conversión.
    
      - En **Regla de conversión**, especifique un patrón para el formato de los números convertidos.
    
    Por ejemplo, si escribe ** ^ \\+\\(d{9}\\+) $** en **coincidencia con este patrón** y **011 $1** en la **regla de traducción**, la regla traducirá + 441235551010 a 011441235551010.

8.  Haga clic en **Aceptar** para guardar la regla de conversión.

9.  Haga clic en **Aceptar** para guardar la configuración de tronco.

10. En la página **Configuración del tronco**, haga clic en **Confirmar** y, a continuación, en **Confirmar todo**.
    
    <div>
    

    > [!NOTE]  
    > Cada vez que cree o modifique una regla de conversión, debe ejecutar el comando <STRONG>Confirmar todo</STRONG> para publicar el cambio de configuración. Para obtener más información, vea <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">publicar cambios pendientes en la configuración de enrutamiento de voz en Lync Server 2013</A> en la documentación de operaciones.

    
    </div>

</div>

<div>

## <a name="see-also"></a>Vea también


[Crear o modificar una regla de traducción con la herramienta generar una regla de traducción de Lync Server 2013](lync-server-2013-create-or-modify-a-translation-rule-by-using-the-build-a-translation-rule-tool.md)  
[Configure a trunk with media bypass in Lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md)  
[Configurar un tronco sin omisión de medios en Lync Server 2013](lync-server-2013-configure-a-trunk-without-media-bypass.md)  
[Publicar los cambios pendientes en la configuración del enrutamiento de voz en Lync Server 2013](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  


[Opciones de omisión de multimedia global en Lync Server 2013](lync-server-2013-global-media-bypass-options.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

