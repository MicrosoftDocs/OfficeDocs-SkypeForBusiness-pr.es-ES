---
title: 'Lync Server 2013: ejecutar la ruta de voz casos de prueba'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Run voice routing test cases
ms:assetid: fb4d32df-b9ea-4944-8cd7-a6102c78c465
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413068(v=OCS.15)
ms:contentKeyID: 48185948
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0cded8f3bf44388103ccf5a33507973817de45ec
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34822401"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="run-voice-routing-test-cases-in-lync-server-2013"></a>Ejecutar los casos de prueba de enrutamiento de voz en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-24_

Puede ejecutar todos los casos de prueba en el conjunto de casos de prueba de enrutamiento de voz, o bien puede ejecutar uno o varios casos de prueba seleccionados.

<div>

## <a name="to-run-all-voice-routing-test-cases"></a>Para ejecutar todos los casos de prueba de enrutamiento de voz

1.  Inicie sesión en el equipo como miembro del grupo RTCUniversalServerAdmins o como miembro del rol CsVoiceAdministrator, CsServerAdministrator o CsAdministrator. Para obtener más información, consulte [permisos de configuración de delegación en Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [abrir las herramientas administrativas 2013 de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **enrutamiento de voz** y luego en **probar enrutamiento de voz**.

4.  En la página **probar enrutamiento de voz** , haga clic en **acción** y, a continuación, en **ejecutar todo**.
    
    El estado de paso o error de cada caso de prueba se muestra en la columna **correcto o error** . Si aún no se ha ejecutado un caso de prueba, se muestra N/A en la columna **correcto o error** .

5.  Faculta Para ver los resultados detallados de cada caso de prueba, haga doble clic en el nombre del caso de prueba. Los resultados se muestran en el área sombreada en el lado derecho de la página **Editar caso de prueba** :
    
    1.  **Resultado de la prueba:** Estado general de paso o error de la ejecución del caso de prueba.
    
    2.  **Regla de normalización:** La primera regla de normalización seleccionada en el plan de marcado para este caso de prueba que coincide con el número marcado (el valor del campo **número para probar** ).
    
    3.  **Número normalizado:** El valor del número marcado después de que la regla de normalización la haya traducido.
    
    4.  **Primer uso de la RTC:** El primer registro de uso de la red telefónica conmutada (RTC) en la Directiva de voz seleccionada para este caso de prueba que coincide con el número marcado.
    
    5.  **Primera ruta:** La primera ruta de voz del primer registro de uso de RTC que coincide con el número marcado.
        
        <div>
        

        > [!NOTE]  
        > El <STRONG>registro de uso de RTC esperado</STRONG> y los campos de <STRONG>ruta</STRONG> previstos son opcionales en la configuración del caso de prueba de enrutamiento de voz. Si el caso de prueba no especifica estos valores, el campo correspondiente en los resultados de la prueba estará vacío.

        
        </div>

</div>

<div>

## <a name="to-run-one-or-more-selected-voice-routing-test-cases"></a>Para ejecutar uno o varios casos de prueba de enrutamiento de voz seleccionados

1.  Inicie sesión en el equipo como miembro del grupo RTCUniversalServerAdmins o como miembro del rol CsVoiceAdministrator, CsServerAdministrator o CsAdministrator. Para obtener más información, consulte [permisos de configuración de delegación en Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [abrir las herramientas administrativas 2013 de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **enrutamiento de voz**y, a continuación, en **probar enrutamiento de voz**.

4.  En la página **probar enrutamiento de voz** , haga clic en los nombres de los casos de prueba que desee ejecutar.

5.  En el menú **acción** , haga clic en **Ejecutar seleccionado**.
    
    El estado de paso o error de cada caso de prueba se muestra en la columna **correcto o error** . Si aún no se ha ejecutado un caso de prueba, se muestra N/A en la columna **correcto o error** .

6.  Faculta Para ver los resultados detallados de cada caso de prueba, haga doble clic en el nombre del caso de prueba. Los resultados se muestran en el área sombreada en el lado derecho de la página **Editar caso de prueba** :
    
    1.  **Resultado de la prueba:** Estado general de paso o error de la ejecución del caso de prueba.
    
    2.  **Regla de normalización:** La primera regla de normalización seleccionada en el plan de marcado para este caso de prueba que coincide con el número marcado (el valor del campo **número para probar** ).
    
    3.  **Número normalizado:** El valor del número marcado después de que la regla de normalización la haya traducido.
    
    4.  **Primer uso de la RTC:** El primer registro de uso de RTC de la Directiva de voz seleccionada para este caso de prueba que coincide con el número marcado.
    
    5.  **Primera ruta:** La primera ruta de voz del primer registro de uso de RTC que coincide con el número marcado.
        
        <div>
        

        > [!NOTE]  
        > El <STRONG>registro de uso de RTC esperado</STRONG> y los campos de <STRONG>ruta</STRONG> previstos son opcionales en la configuración del caso de prueba de enrutamiento de voz. Si el caso de prueba no especifica estos valores, el campo correspondiente en los resultados de la prueba estará vacío.

        
        </div>

</div>

<div>

## <a name="see-also"></a>Vea también


[Probar el enrutamiento de voz en Lync Server 2013](lync-server-2013-test-voice-routing.md)  
[Ejecución de pruebas de enrutamiento de voz en Lync Server 2013](lync-server-2013-running-voice-routing-tests.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

