---
title: "Lync Server 2013 : Créa. ou modification manuelle d’une règle de normalisation"
TOCTitle: Crear o modificar una regla de normalización manualmente
ms:assetid: fc0335e6-8830-4cfb-8c64-6aeb98c0a992
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg413074(v=OCS.15)
ms:contentKeyID: 48277288
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Crear o modificar una regla de normalización manualmente en Lync Server 2013

 

_**Última modificación del tema:** 2012-09-22_

Siga los pasos que se muestran a continuación si desea crear o modificar manualmente una regla de normalización. Si desea crear o modificar una regla de normalización mediante Generar regla de normalización en Panel de control de Lync Server, vea [Crear o modificar una regla de normalización mediante Crear una regla de normalización en Lync Server 2013](lync-server-2013-create-or-modify-a-normalization-rule-by-using-build-a-normalization-rule.md).

## Para definir una regla de normalización de forma manual

1.  Inicie sesión en el equipo como miembro del grupo RTCUniversalServerAdmins o como miembro del rol CsVoiceAdministrator, CsServerAdministrator o CsAdministrator. Para más información, consulte [Delegar permisos de instalación en Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Abra una ventana del explorador y después introduzca la dirección URL de administración para abrir el panel de control de Lync Server. Para más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Abrir las herramientas administrativas de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  (Opcional) Siga los pasos que se indican en [Crear un plan de marcado en Lync Server 2013](lync-server-2013-create-a-dial-plan.md) o [Modificar un plan de marcado en Lync Server 2013](lync-server-2013-modify-a-dial-plan.md).

4.  En **Nueva regla de normalización** o **Editar regla de normalización**, escriba un nombre que describa el patrón numérico que se normalizará en **Nombre** (por ejemplo, llame a la regla de normalización **Extension5digitos**).

5.  (Opcional) En el campo **Descripción**, escriba una descripción de la regla de normalización (por ejemplo, "Convierte extensiones de 5 dígitos").

6.  En **Generar regla de normalización**, haga clic en **Editar**.

7.  Especifique lo siguiente en **Escribir una expresión regular**:
    
      - En **Hacer coincidir este patrón**, especifique el patrón que desee usar para obtener como resultado el número de teléfono marcado.
    
      - En **Regla de conversión**, especifique un patrón para el formato de los números de teléfono E.164 convertidos.
    
    Por ejemplo, si especifica **^(\\d{7})$** en el campo **Hacer coincidir este patrón** y **+1425$1** en el campo **Regla de conversión**, la regla convertirá 5550100 en +14255550100.

8.  (Opcional) Si la regla de normalización da un número de teléfono interno de la organización, seleccione **Extensión interna**.

9.  (Opcional) Especifique un número para probar la regla de normalización y, a continuación, haga clic en **Ir**. Los resultados de la prueba se muestran en **Introducir un número para probarlo**.
    

    > [!NOTE]
    > Puede guardar una regla de normalización que aún no haya pasado la prueba y volver a configurarla más adelante. Para obtener información detallada, vea <A href="lync-server-2013-test-voice-routing.md">Probar el enrutamiento de voz en Lync Server 2013</A>.



10. Haga clic en **Aceptar** para guardar la regla de normalización.

11. Haga clic en **Aceptar** para guardar el plan de marcado.

12. En la página **Plan de marcado**, haga clic en **Confirmar** y, a continuación, en **Confirmar todo**.
    

    > [!NOTE]
    > Cada vez que cree o cambie una regla de normalización, debe ejecutar el comando <STRONG>Confirmar todo</STRONG> para publicar el cambio de configuración. Para obtener información detallada, vea <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publicar los cambios pendientes en la configuración del enrutamiento de voz en Lync Server 2013</A> en la documentación referente a las operaciones.



## Vea también

#### Tareas

[Crear o modificar una regla de normalización mediante Crear una regla de normalización en Lync Server 2013](lync-server-2013-create-or-modify-a-normalization-rule-by-using-build-a-normalization-rule.md)  
[Crear un plan de marcado en Lync Server 2013](lync-server-2013-create-a-dial-plan.md)  
[Modificar un plan de marcado en Lync Server 2013](lync-server-2013-modify-a-dial-plan.md)  
[Publicar los cambios pendientes en la configuración del enrutamiento de voz en Lync Server 2013](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  

#### Otros recursos

[Probar el enrutamiento de voz en Lync Server 2013](lync-server-2013-test-voice-routing.md)

