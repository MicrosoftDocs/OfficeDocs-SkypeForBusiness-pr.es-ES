---
title: "Crear o modificar regla de conversión mediante Generar una regla de conversión"
TOCTitle: "Créer ou mod. une règle de trad. à l’aide de l’outil Créer une règle de trad."
ms:assetid: ba112df8-3bb4-48e4-a353-4bf9110ccd71
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg412909(v=OCS.15)
ms:contentKeyID: 48276489
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Crear o modificar una regla de conversión mediante la herramienta Generar una regla de conversión

 

_**Última modificación del tema:** 2012-10-05_

Siga estos pasos si desea definir una regla de conversión especificando un conjunto de valores en la herramienta **Construir una regla de conversión** y habilitando Panel de control de Lync Server para que genere el patrón de correspondencia y regla de conversión apropiados para usted. De forma alternativa, puede escribir una expresión regular manualmente para definir el patrón de correspondencia y regla de conversión. Para obtener información detallada, consulte [Crear o modificar una regla de conversión manualmente](lync-server-2013-create-or-modify-a-translation-rule-manually.md).

## Para definir una regla mediante el uso de la herramienta Construir una regla de conversión

1.  Inicie sesión en el equipo como miembro del grupo RTCUniversalServerAdmins o como miembro del rol CsVoiceAdministrator, CsServerAdministrator o CsAdministrator. Para más información, consulte [Delegar permisos de instalación en Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Abra una ventana del explorador y después introduzca la dirección URL de administración para abrir el panel de control de Lync Server. Para más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Abrir las herramientas administrativas de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Para empezar a definir una regla de conversión, siga los pasos de [Configurar un tronco con omisión de medios en Lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md) hasta el paso 10 o de [Configurar un tronco sin omisión de medios en Lync Server 2013](lync-server-2013-configure-a-trunk-without-media-bypass.md) hasta el paso 9.

4.  En **Nombre**, en las páginas **Nueva regla de conversión** o **Editar regla de conversión**, escriba un nombre que describa el patrón de número objeto de la conversión.

5.  (Opcional) En **Descripción**, escriba una descripción de la regla de conversión, por ejemplo **Marcado de larga distancia internacional de EE.UU.**.

6.  En la sección **Construir una regla de conversión** del cuadro de diálogo, especifique valores en los campos siguientes:
    
      - **Dígitos iniciales**: (opcional) especifique los dígitos iniciales de los números para los que desea que coincida el patrón. Por ejemplo, escriba **+** en este campo para que se cree una correspondencia con números en formato E.164 (que comiencen con +).
    
      - **Longitud**: especifique el número de dígitos en el patrón de coincidencia y seleccione si desea que el patrón coincida con números de exactamente esta longitud, al menos esta longitud o de cualquier longitud. Por ejemplo, escriba **11** y seleccione **Como mínimo** en la lista desplegable para que haya coincidencias con números de al menos 11 dígitos de longitud.
    
      - **Dígitos que se van a quitar**: (opcional) especifique el número de dígitos iniciales que se van a quitar. Por ejemplo, escriba **1** para quitar el **+** del comienzo del número.
    
      - **Dígitos que se van a agregar**: (opcional) especifique los dígitos que se van a agregar a los números convertidos. Por ejemplo, escriba **011** si desea que se agregue 011 a los números convertidos cuando se aplique la regla.
    
    Los valores que especifique en estos campos se reflejarán en los campos **Patrón con el que hacer coincidir** y **Reglas de conversión**. Por ejemplo, si especifica los valores de ejemplo precedentes, la expresión regular resultante en el campo **Patrón con el que hacer coincidir** es:
    
    **^\\+(\\d{9}\\d+)$**
    
    El campo **Regla de conversión**, especifica un patrón para el formato de los números convertidos. Este patrón tiene dos partes:
    
      - Un valor (por ejemplo, **$1**) que representa el número de dígitos en el patrón con el que hacer coincidir.
    
      - (Opcional) Un valor que puede agregar si lo especifica en el campo **Dígitos a agregar**.
    
    Al usar los valores del ejemplo anterior, aparecerá **011$1** en el campo **Regla de conversión**.
    
    Cuando la regla de conversión se aplique, +441235551010 se convertirá en 011441235551010.

7.  Haga clic en **Aceptar** para guardar la regla de conversión.

8.  Haga clic en **Aceptar** para guardar la configuración de tronco.

9.  En la página **Configuración del tronco**, haga clic en **Confirmar** y, a continuación, en **Confirmar todo**.
    

    > [!NOTE]
    > Siempre que cree o modifique una regla de conversión, debe ejecutar el comando <STRONG>Confirmar todo</STRONG> para publicar el cambio en la configuración. Para obtener más información, consulte <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publicar los cambios pendientes en la configuración del enrutamiento de voz en Lync Server 2013</A> en la documentación referente a las operaciones.



## Vea también

#### Tareas

[Crear o modificar una regla de conversión manualmente](lync-server-2013-create-or-modify-a-translation-rule-manually.md)  
[Configurar un tronco con omisión de medios en Lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md)  
[Configurar un tronco sin omisión de medios en Lync Server 2013](lync-server-2013-configure-a-trunk-without-media-bypass.md)  
[Publicar los cambios pendientes en la configuración del enrutamiento de voz en Lync Server 2013](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  

#### Conceptos

[Opciones globales de desvío de medios en Lync Server 2013](lync-server-2013-global-media-bypass-options.md)

