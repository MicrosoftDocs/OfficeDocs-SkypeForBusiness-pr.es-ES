---
title: Crear o modificar una regla de traducción con la herramienta generar una regla de traducción
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create or modify a translation rule by using the Build a Translation Rule tool
ms:assetid: ba112df8-3bb4-48e4-a353-4bf9110ccd71
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412909(v=OCS.15)
ms:contentKeyID: 48185224
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 06f498af25dfd851bd2950ce08d5c66179b95ebc
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34835782"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-translation-rule-by-using-the-build-a-translation-rule-tool-in-lync-server-2013"></a>Crear o modificar una regla de traducción con la herramienta generar una regla de traducción de Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-05_

Siga estos pasos si desea definir una regla de traducción escribiendo un conjunto de valores en la herramienta **generar una regla de traducción** y habilitando el panel de control de Lync Server para generar la regla de traducción y el patrón de coincidencia correspondiente. También tiene la opción de escribir una expresión regular manualmente para definir el patrón de correspondencia y la regla de conversión. Para obtener más información, vea [crear o modificar una regla de traducción de forma manual en Lync Server 2013](lync-server-2013-create-or-modify-a-translation-rule-manually.md).

<div>

## <a name="to-define-a-rule-by-using-the-build-a-translation-rule-tool"></a>Para definir una regla mediante el uso de la herramienta Crear una regla de conversión

1.  Inicie sesión en el equipo como miembro del grupo RTCUniversalServerAdmins o como miembro del rol CsVoiceAdministrator, CsServerAdministrator o CsAdministrator. Para obtener más información, consulte [permisos de configuración de delegación en Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [abrir las herramientas administrativas 2013 de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Para empezar a definir una regla de traducción, siga los pasos que se indican en [configurar un tronco con la omisión de medios en Lync server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md) hasta el paso 10 o [configurar un tronco sin evitar los medios en Lync Server 2013](lync-server-2013-configure-a-trunk-without-media-bypass.md) a paso 9.

4.  En **Nombre**, en las páginas **Nueva regla de conversión** o **Editar regla de conversión**, escriba un nombre que describa el patrón de número objeto de la conversión.

5.  (Opcional) En **Descripción**, escriba una descripción de la regla de conversión, por ejemplo, **US International long-distance dialing**.

6.  En la sección **Crear una regla de conversión** del cuadro de diálogo, especifique valores en los campos siguientes:
    
      - **Dígitos iniciales**: (opcional) especifique los dígitos iniciales de los números para los que desea que coincida el patrón. Por ejemplo, escriba **+** en este campo para encontrarse números en formato E. 164 (que comienzan con +).
    
      - **Longitud**: especifique el número de dígitos en el patrón de coincidencia y seleccione si desea que el patrón coincida con números de exactamente esta longitud, al menos esta longitud o de cualquier longitud. Por ejemplo, escriba **11** y seleccione **At least** en la lista desplegable para que haya coincidencias con números de al menos 11 dígitos de longitud.
    
      - **Dígitos que se van a quitar**: (opcional) especifique el número de dígitos iniciales que se van a quitar. Por ejemplo, escriba **1** para quitar el **+** principio del número.
    
      - **Dígitos que se van a agregar**: (opcional) especifique los dígitos que se van a agregar a los números convertidos. Por ejemplo, escriba **011** si desea que se agregue 011 a los números convertidos cuando se aplique la regla.
    
    Los valores que especifique en estos campos se reflejarán en los campos **Patrón con el que hacer coincidir** y **Regla de conversión**. Por ejemplo, si especifica los valores de ejemplo precedentes, la expresión regular resultante en el campo **Patrón con el que hacer coincidir** es:
    
    **^\\+ (\\d{9}\\+) $**
    
    El campo **Regla de conversión** especifica un patrón para el formato de los números convertidos. Este patrón tiene dos partes:
    
      - Un valor (por ejemplo, **$1**) que representa el número de dígitos en el patrón con el que hacer coincidir.
    
      - (Opcional) Un valor que puede agregar si lo especifica en el campo **Dígitos a agregar**.
    
    Al usar los valores del ejemplo anterior, aparecerá **011$1** en el campo **Regla de conversión**.
    
    Cuando la regla de conversión se aplique, +441235551010 se convertirá en 011441235551010.

7.  Haga clic en **Aceptar** para guardar la regla de conversión.

8.  Haga clic en **Aceptar** para guardar la configuración de tronco.

9.  En la página **Configuración del tronco**, haga clic en **Confirmar** y, a continuación, en **Confirmar todo**.
    
    <div>
    

    > [!NOTE]
    > Cada vez que cree o modifique una regla de conversión, debe ejecutar el comando <STRONG>Confirmar todo</STRONG> para publicar el cambio de configuración. Para obtener más información, vea <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">publicar cambios pendientes en la configuración de enrutamiento de voz en Lync Server 2013</A> en la documentación de operaciones.

    
    </div>

</div>

<div>

## <a name="see-also"></a>Vea también


[Crear o modificar una regla de traducción de forma manual en Lync Server 2013](lync-server-2013-create-or-modify-a-translation-rule-manually.md)  
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

