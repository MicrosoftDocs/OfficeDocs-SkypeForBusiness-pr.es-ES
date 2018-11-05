---
title: "Exéc. les cas de test du routage des comm. voc. dans Lync Server 2013"
TOCTitle: "Exéc. les cas de test du routage des comm. voc. dans Lync Server 2013"
ms:assetid: fb4d32df-b9ea-4944-8cd7-a6102c78c465
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg413068(v=OCS.15)
ms:contentKeyID: 48277283
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Ejecutar casos de prueba de enrutamiento en Lync Server 2013

 

_**Última modificación del tema:** 2013-02-24_

Puede ejecutar todos los casos de prueba de su conjunto de casos de prueba de enrutamiento de voz, o bien ejecutar uno o varios casos de prueba seleccionados.

## Para ejecutar todos los casos de prueba de enrutamiento de voz

1.  Inicie sesión en el equipo como miembro del grupo RTCUniversalServerAdmins o como miembro del rol CsVoiceAdministrator, CsServerAdministrator o CsAdministrator. Para más información, consulte [Delegar permisos de instalación en Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Abra una ventana del explorador y después introduzca la dirección URL de administración para abrir el panel de control de Lync Server. Para más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Abrir las herramientas administrativas de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Enrutamiento de voz** y, a continuación, en **Probar enrutamiento de voz**.

4.  En la página **Probar enrutamiento de voz**, haga clic en **Acción** y, a continuación, en **Ejecutar todo**.
    
    El estado de superado o no superado con respecto a cada caso de prueba se muestra en la columna **Superado/no superado**. Si no se ha ejecutado aún ningún caso de prueba, aparecerá N/A en la columna **Superado/no superado**.

5.  (Opcional) Para ver los resultados detallados de cada caso de prueba, haga doble clic en el nombre del caso de prueba que desee. Los resultados se muestran en la zona sombreada a la derecha de la página **Editar caso de prueba**.
    
    1.  **Resultado de la prueba:** Estado global de superado o no superado para el caso de prueba ejecutado.
    
    2.  **Regla de normalización:** La primera regla de normalización en el plan de marcado seleccionado para el caso de prueba que coincide con el número marcado (el valor en el campo **Número a probar**).
    
    3.  **Número normalizado:** El valor del número marcado después de que la regla de normalización lo haya convertido.
    
    4.  **Primer uso de RTC:** El primer registro de uso de RTC en la directiva de voz que se ha seleccionado para este caso de prueba que coincide con el número marcado.
    
    5.  **Primera ruta:** La primera ruta de voz en el registro de uso de RTC que coincida con el número marcado.
        

        > [!NOTE]
        > Los campos <STRONG>Registro de uso de RTC previsto</STRONG> y <STRONG>Ruta prevista</STRONG> son opcionales en la configuración del caso de prueba de enrutamiento de voz. Si el caso de prueba no especifica estos valores, el campo correspondiente en los resultados de la prueba estará vacío.



## Para ejecutar uno o varios casos de prueba de enrutamiento de voz seleccionados

1.  Inicie sesión en el equipo como miembro del grupo RTCUniversalServerAdmins o como miembro del rol CsVoiceAdministrator, CsServerAdministrator o CsAdministrator. Para más información, consulte [Delegar permisos de instalación en Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Abra una ventana del explorador y después introduzca la dirección URL de administración para abrir el panel de control de Lync Server. Para más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Abrir las herramientas administrativas de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Enrutamiento de voz** y, a continuación, en **Probar enrutamiento de voz**.

4.  En la página **Probar enrutamiento de voz**, haga clic en los nombres de los casos de prueba que desee ejecutar.

5.  En el menú **Acción**, haga clic en **Ejecutar seleccionados**.
    
    El estado de superado o no superado con respecto a cada caso de prueba se muestra en la columna **Superado/no superado**. Si no se ha ejecutado aún ningún caso de prueba, aparecerá N/A en la columna **Superado/no superado**.

6.  (Opcional) Para ver los resultados detallados de cada caso de prueba, haga doble clic en el nombre del caso de prueba que desee. Los resultados se muestran en la zona sombreada a la derecha de la página **Editar caso de prueba**.
    
    1.  **Resultado de la prueba:** Estado global de superado o no superado para el caso de prueba ejecutado.
    
    2.  **Regla de normalización:** La primera regla de normalización en el plan de marcado seleccionado para el caso de prueba que coincide con el número marcado (el valor en el campo **Número a probar**).
    
    3.  **Número normalizado:** El valor del número marcado después de que la regla de normalización lo haya convertido.
    
    4.  **Primer uso de RTC:** El primer registro de uso de RTC en la directiva de voz que se ha seleccionado para este caso de prueba que coincide con el número marcado.
    
    5.  **Primera ruta:** La primera ruta de voz en el registro de uso de RTC que coincida con el número marcado.
        

        > [!NOTE]
        > Los campos <STRONG>Registro de uso de RTC previsto</STRONG> y <STRONG>Ruta prevista</STRONG> son opcionales en la configuración del caso de prueba de enrutamiento de voz. Si el caso de prueba no especifica estos valores, el campo correspondiente en los resultados de la prueba estará vacío.



## Vea también

#### Otros recursos

[Probar el enrutamiento de voz en Lync Server 2013](lync-server-2013-test-voice-routing.md)  
[Ejecución de pruebas de enrutamiento de voz en Lync Server 2013](lync-server-2013-running-voice-routing-tests.md)

