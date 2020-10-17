---
title: 'Lync Server 2013: ejecutar los casos de prueba de enrutamiento de voz'
description: 'Lync Server 2013: ejecutar los casos de prueba de enrutamiento de voz.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Run voice routing test cases
ms:assetid: fb4d32df-b9ea-4944-8cd7-a6102c78c465
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413068(v=OCS.15)
ms:contentKeyID: 48185948
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e521216a12fba6b78913e7f4a79432809bb6e252
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566796"
---
# <a name="run-voice-routing-test-cases-in-lync-server-2013"></a>Ejecutar casos de prueba de enrutamiento de voz en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-24_

Puede ejecutar todos los casos de prueba en el conjunto de casos de prueba de enrutamiento de voz, o bien puede ejecutar uno o varios casos de prueba seleccionados.

<div>

## <a name="to-run-all-voice-routing-test-cases"></a>Para ejecutar todos los casos de prueba de enrutamiento de voz

1.  Inicie sesión en el equipo como miembro del grupo RTCUniversalServerAdmins o como miembro de la función CsVoiceAdministrator, CsServerAdministrator o CsAdministrator. Para obtener más información, consulte [Delegate Setup Permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Enrutamiento de voz** y, a continuación, en **Probar enrutamiento de voz**.

4.  En la página **Probar enrutamiento de voz**, haga clic en **Acción** y, a continuación, en **Ejecutar todo**.
    
    El estado de superado o no superado con respecto a cada caso de prueba se muestra en la columna **Superado/no superado**. Si no se ha ejecutado aún ningún caso de prueba, aparecerá N/A en la columna **Superado/no superado**.

5.  (Opcional) Para ver los resultados detallados de cada caso de prueba, haga doble clic en el nombre del caso de prueba que desee. Los resultados se muestran en la zona sombreada a la derecha de la página **Editar caso de prueba**.
    
    1.  **Resultado de la prueba:** Estado general de Pass o Fail del caso de prueba ejecutado.
    
    2.  **Regla de normalización:** La primera regla de normalización del plan de marcado seleccionado para este caso de prueba que coincide con el número marcado (el valor del campo **número que se va a probar** ).
    
    3.  **Número normalizado:** El valor del número marcado después de que la regla de normalización la haya traducido.
    
    4.  **Primer uso de RTC:** El primer registro de uso de RTC (red telefónica conmutada) en la Directiva de voz seleccionada para este caso de prueba que coincide con el número marcado.
    
    5.  **Primera ruta:** La primera ruta de voz del primer registro de uso de RTC que coincide con el número marcado.
        
        <div>
        

        > [!NOTE]  
        > Los campos <STRONG>Registro de uso de RTC previsto</STRONG> y <STRONG>Ruta prevista</STRONG> son opcionales en la configuración del caso de prueba de enrutamiento de voz. Si el caso de prueba no especifica estos valores, el campo correspondiente en los resultados de la prueba estará vacío.

        
        </div>

</div>

<div>

## <a name="to-run-one-or-more-selected-voice-routing-test-cases"></a>Para ejecutar uno o varios casos de prueba de enrutamiento de voz seleccionados

1.  Inicie sesión en el equipo como miembro del grupo RTCUniversalServerAdmins o como miembro de la función CsVoiceAdministrator, CsServerAdministrator o CsAdministrator. Para obtener más información, consulte [Delegate Setup Permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Enrutamiento de voz** y, a continuación, en **Probar enrutamiento de voz**.

4.  En la página **Probar enrutamiento de voz**, haga clic en los nombres de los casos de prueba que desee ejecutar.

5.  En el menú **Acción**, haga clic en **Ejecutar seleccionados**.
    
    El estado de superado o no superado con respecto a cada caso de prueba se muestra en la columna **Superado/no superado**. Si no se ha ejecutado aún ningún caso de prueba, aparecerá N/A en la columna **Superado/no superado**.

6.  (Opcional) Para ver los resultados detallados de cada caso de prueba, haga doble clic en el nombre del caso de prueba que desee. Los resultados se muestran en la zona sombreada a la derecha de la página **Editar caso de prueba**.
    
    1.  **Resultado de la prueba:** Estado general de Pass o Fail del caso de prueba ejecutado.
    
    2.  **Regla de normalización:** La primera regla de normalización del plan de marcado seleccionado para este caso de prueba que coincide con el número marcado (el valor del campo **número que se va a probar** ).
    
    3.  **Número normalizado:** El valor del número marcado después de que la regla de normalización la haya traducido.
    
    4.  **Primer uso de RTC:** El primer registro de uso de RTC en la Directiva de voz que se ha seleccionado para este caso de prueba que coincide con el número marcado.
    
    5.  **Primera ruta:** La primera ruta de voz del primer registro de uso de RTC que coincide con el número marcado.
        
        <div>
        

        > [!NOTE]  
        > Los campos <STRONG>Registro de uso de RTC previsto</STRONG> y <STRONG>Ruta prevista</STRONG> son opcionales en la configuración del caso de prueba de enrutamiento de voz. Si el caso de prueba no especifica estos valores, el campo correspondiente en los resultados de la prueba estará vacío.

        
        </div>

</div>

<div>

## <a name="see-also"></a>Consulte también


[Probar el enrutamiento de voz en Lync Server 2013](lync-server-2013-test-voice-routing.md)  
[Ejecución de pruebas de enrutamiento de voz en Lync Server 2013](lync-server-2013-running-voice-routing-tests.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

