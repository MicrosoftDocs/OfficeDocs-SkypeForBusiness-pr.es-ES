---
title: "Crear/modificar una regla de normalización mediante Crear una regla de normalización"
TOCTitle: Crear o modificar una regla de normalización mediante Crear una regla de normalización
ms:assetid: e8547d7b-f74d-4a73-9a7d-df20d7a87fcd
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg399036(v=OCS.15)
ms:contentKeyID: 48277031
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Crear o modificar una regla de normalización mediante Crear una regla de normalización en Lync Server 2013

 

_**Última modificación del tema:** 2012-11-01_

Siga los pasos que se indican a continuación si desea crear o modificar una regla de normalización en Panel de control de Lync Server. Otra opción, para crear o modificar manualmente una regla de normalización, es consultar [Crear o modificar una regla de normalización manualmente en Lync Server 2013](lync-server-2013-create-or-modify-a-normalization-rule-manually.md).

## Para definir una regla mediante Generar regla de normalización

1.  Inicie sesión en el equipo como miembro del grupo RTCUniversalServerAdmins o como miembro del rol CsVoiceAdministrator, CsServerAdministrator o CsAdministrator. Para más información, consulte [Delegar permisos de instalación en Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Abra una ventana del explorador y después introduzca la dirección URL de administración para abrir el panel de control de Lync Server. Para más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Abrir las herramientas administrativas de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  (Opcional) Siga los pasos que se indican en [Crear un plan de marcado en Lync Server 2013](lync-server-2013-create-a-dial-plan.md), hasta el paso 11, o [Modificar un plan de marcado en Lync Server 2013](lync-server-2013-modify-a-dial-plan.md), hasta el paso 10.

4.  En **Nueva regla de normalización** o **Editar regla de normalización** , escriba un nombre que describa el patrón numérico que se normalizará en **Nombre** (por ejemplo, **Extension5digitos** ).

5.  (Opcional) En **Descripción** , escriba una descripción de la regla de normalización (por ejemplo, "Convierte extensiones de 5 dígitos").

6.  En **Generar regla de normalización** , escriba valores en los siguientes campos:
    
      - **Dígitos iniciales**    (Opcional) Especifique los primeros dígitos de los números marcados que desee que coincidan con el patrón. Por ejemplo, escriba **425** si desea que el patrón coincida con los números marcados que empiecen por 425.
    
      - **Longitud**    Especifique la cantidad de dígitos del patrón y seleccione si desea que el patrón coincida exactamente con esta longitud, con los números marcados que tengan como mínimo esta longitud o con los números marcados de cualquier longitud.
    
      - **Dígitos que se quitarán**    (Opcional) Especifique la cantidad de dígitos iniciales que se quitarán de los números marcados con los que desea que coincida el patrón.
    
      - **Dígitos que se agregarán**    (Opcional) Especifique los dígitos que se agregarán a los números marcados con los que desea que coincida el patrón.
    
    Los valores que introduzca en estos campos se reflejarán en **Patrón con el que hacer coincidir** y **Regla de conversión** . Por ejemplo, si deja en blanco **Dígitos iniciales** , escriba **7** en el campo **Longitud** y seleccione **Exactamente** , e introduzca **0** en **Dígitos que se quitarán** , la expresión regular que se creará como resultado en **Patrón con el que hacer coincidir** es:
    
    **^(\\d{7})$**

7.  En **Regla de conversión** , especifique un patrón para el formato de los números de teléfono E.164 convertidos, así:
    
      - Un valor que represente la cantidad de dígitos especificada en el patrón de coincidencia. Por ejemplo, si el patrón de coincidencia es **^(\\d{7})$** , **$1** en la regla de conversión representará a los números marcados de 7 dígitos.
    
      - (Opcional) Escriba un valor en el campo **Dígitos que se agregarán** para especificar los dígitos que se agregarán al principio del número convertido (por ejemplo, **+1425** ).
    
    Por ejemplo, si **Patrón con el que hacer coincidir** contiene **^(\\d{7})$** como patrón para los números marcados y **Regla de conversión** contiene **+1425$1** como patrón para los números de teléfono E.164, la regla normalizará 5550100 como +14255550100.

8.  (Opcional) Si la regla de normalización da un número de teléfono interno de la organización, seleccione **Extensión interna** .

9.  (Opcional) Especifique un número para probar la regla de normalización y después haga clic en **Ir** . Los resultados de la prueba se muestran en **Introducir un número para probarlo** .
    

    > [!NOTE]
    > Puede guardar una regla de normalización que aún no haya pasado la prueba y volver a configurarla más adelante. Para más información, consulte <A href="lync-server-2013-test-voice-routing.md">Probar el enrutamiento de voz en Lync Server 2013</A>.



10. Haga clic en **Aceptar** para guardar la regla de normalización.

11. Haga clic en **Aceptar** para guardar el plan de marcado.

12. En la página **Plan de marcado** , haga clic en **Confirmar** y, a continuación, en **Confirmar todo** .
    

    > [!NOTE]
    > Cada vez que cree o cambie una regla de normalización, debe ejecutar el comando <STRONG>Confirmar todo</STRONG> para publicar el cambio de configuración. Para más información, consulte <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publicar los cambios pendientes en la configuración del enrutamiento de voz en Lync Server 2013</A> en la documentación referente a las operaciones.



## Vea también

#### Tareas

[Crear o modificar una regla de normalización manualmente en Lync Server 2013](lync-server-2013-create-or-modify-a-normalization-rule-manually.md)  
[Crear un plan de marcado en Lync Server 2013](lync-server-2013-create-a-dial-plan.md)  
[Modificar un plan de marcado en Lync Server 2013](lync-server-2013-modify-a-dial-plan.md)  
[Publicar los cambios pendientes en la configuración del enrutamiento de voz en Lync Server 2013](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  

#### Otros recursos

[Probar el enrutamiento de voz en Lync Server 2013](lync-server-2013-test-voice-routing.md)

