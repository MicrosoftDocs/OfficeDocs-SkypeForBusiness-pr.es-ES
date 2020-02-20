---
title: Creación o modificación de una regla de conversión mediante la herramienta generar una regla de conversión
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a translation rule by using the Build a Translation Rule tool
ms:assetid: ba112df8-3bb4-48e4-a353-4bf9110ccd71
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412909(v=OCS.15)
ms:contentKeyID: 48185224
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8c529a83a85cd9ffbed0aa0b5e9a741e6c3a7815
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151822"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-translation-rule-by-using-the-build-a-translation-rule-tool-in-lync-server-2013"></a>Crear o modificar una regla de conversión mediante la herramienta generar una regla de conversión en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-05_

Siga estos pasos si desea definir una regla de conversión introduciendo un conjunto de valores en la herramienta **generar una regla de conversión** y habilitando el panel de control de Lync Server para generar el patrón de coincidencia y la regla de conversión correspondientes. Como alternativa, puede escribir manualmente una expresión regular para definir el patrón de coincidencia y la regla de conversión. Para obtener más información, consulte [crear o modificar una regla de conversión de forma manual en Lync Server 2013](lync-server-2013-create-or-modify-a-translation-rule-manually.md).

<div>

## <a name="to-define-a-rule-by-using-the-build-a-translation-rule-tool"></a>Para definir una regla mediante la herramienta generar una regla de conversión

1.  Inicie sesión en el equipo como miembro del grupo RTCUniversalServerAdmins o como miembro de la función CsVoiceAdministrator, CsServerAdministrator o CsAdministrator. Para obtener más información, consulte [Delegate Setup Permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Para empezar a definir una regla de conversión, siga los pasos que se indican en [configurar un tronco con la omisión de medios en Lync server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md) hasta el paso 10 o [configurar un tronco sin omisión de medios en Lync Server 2013](lync-server-2013-configure-a-trunk-without-media-bypass.md) a paso 9.

4.  En **nombre** en la página **nueva regla de conversión** o **Editar regla de conversión** , escriba un nombre que describa el patrón de número que se va a traducir.

5.  Opcional En **Descripción**, escriba una descripción de la regla de conversión, por ejemplo, **US International Long-Distance dialing**.

6.  En la sección **crear una regla de conversión** del cuadro de diálogo, escriba los valores en los campos siguientes:
    
      - **Dígitos iniciales**: (opcional) especifique los dígitos iniciales de los números con los que desea que se ajuste la trama. Por ejemplo, escriba **+** en este campo para hacer coincidir números en formato E. 164 (que comienzan con +).
    
      - **Longitud**: especifique el número de dígitos en el patrón de coincidencia y seleccione si desea que el patrón coincida exactamente con los números que tengan esta longitud, como mínimo, esta longitud o cualquier longitud. Por ejemplo, escriba **11** y seleccione **al menos** en la lista desplegable para hacer coincidir los números con una longitud de al menos 11 dígitos.
    
      - **Dígitos que se quitarán**: (opcional) especifique el número de dígitos iniciales que se quitarán. Por ejemplo, escriba **1** para quitar el **+** principio del número.
    
      - **Dígitos que se agregarán**: (opcional) especifique los dígitos que se van a anteponer a los números convertidos. Por ejemplo, escriba **011** si desea anteponer 011 a los números convertidos cuando se aplica la regla.
    
    Los valores que escriba en estos campos se reflejarán en los campos **patrón para coincidir** y **regla de conversión** . Por ejemplo, si especifica los valores de ejemplo anteriores, la expresión regular resultante del **patrón para coincidir con** el campo es:
    
    **^\\+ (\\d{9}\\d +) $**
    
    El campo **regla de conversión** especifica un patrón para el formato de los números convertidos. Este patrón consta de dos partes:
    
      - Un valor (por ejemplo, **$1**) que representa el número de dígitos en el patrón de coincidencia.
    
      - Opcional Un valor que puede anteponer si lo especifica en el campo **dígitos que se agregarán**
    
    Con los valores del ejemplo anterior, se muestra **011 $1** en el campo **regla de conversión** .
    
    Cuando se aplica esta regla de conversión, + 441235551010 se convierte en 011441235551010.

7.  Haga clic en **Aceptar** para guardar la regla de conversión.

8.  Haga clic en **Aceptar** para guardar la configuración de tronco.

9.  En la página **Configuración de tronco**, haga clic en **Confirmar** y, a continuación, en **Confirmar todo**.
    
    <div>
    

    > [!NOTE]
    > Siempre que cree o modifique una regla de conversión, debe ejecutar el comando <STRONG>Confirmar todo</STRONG> para publicar el cambio en la configuración. Para obtener más información, consulte <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish Pending changes to the Voice Routing Configuration en Lync Server 2013</A> en la documentación de operaciones.

    
    </div>

</div>

<div>

## <a name="see-also"></a>Vea también


[Crear o modificar una regla de conversión de forma manual en Lync Server 2013](lync-server-2013-create-or-modify-a-translation-rule-manually.md)  
[Configurar un tronco con la omisión de medios en Lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md)  
[Configurar un tronco sin omisión de medios en Lync Server 2013](lync-server-2013-configure-a-trunk-without-media-bypass.md)  
[Publicar los cambios pendientes en la configuración del enrutamiento de voz en Lync Server 2013](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  


[Opciones de omisión de medios globales en Lync Server 2013](lync-server-2013-global-media-bypass-options.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

