---
title: Crear o modificar una regla de conversión manualmente
TOCTitle: Crear o modificar una regla de conversión manualmente
ms:assetid: 049d1db3-af58-48c5-be89-52e1d068a4bd
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg398099(v=OCS.15)
ms:contentKeyID: 48274284
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Crear o modificar una regla de conversión manualmente

 

_**Última modificación del tema:** 2012-08-06_

Siga estos pasos si desea definir una regla de conversión escribiendo una expresión regular para el patrón de coincidencia y la regla de conversión. De forma alternativa, puede especificar un grupo de valores en la herramienta **Generar una regla de conversión** y permitir que Panel de control de Lync Server genere el patrón de coincidencia y la regla de conversión correspondiente. Para obtener más información, consulte [Crear o modificar una regla de conversión mediante la herramienta Generar una regla de conversión](lync-server-2013-create-or-modify-a-translation-rule-by-using-the-build-a-translation-rule-tool.md).

## Para definir una regla de conversión de forma manual

1.  Inicie sesión en el equipo como miembro del grupo RTCUniversalServerAdmins o como miembro del rol CsVoiceAdministrator, CsServerAdministrator o CsAdministrator. Para más información, consulte [Delegar permisos de instalación en Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Abra una ventana del explorador y después introduzca la dirección URL de administración para abrir el panel de control de Lync Server. Para más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Abrir las herramientas administrativas de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Para empezar a definir una regla de conversión, siga los pasos de [Configurar un tronco con omisión de medios en Lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md) hasta el paso 10 o de [Configurar un tronco sin omisión de medios en Lync Server 2013](lync-server-2013-configure-a-trunk-without-media-bypass.md) hasta el paso 9.

4.  En el campo **Nombre** en las páginas **Nueva regla de conversión** o **Editar regla de conversión**, escriba un nombre que describa el patrón de número de objeto de la conversión.

5.  (Opcional) En **Descripción**, escriba una descripción de la regla de conversión, por ejemplo **Marcado de larga distancia internacional de EE.UU.**.

6.  Haga clic en **Editar** en la parte inferior de la sección **Generar una regla de conversión**.

7.  Especifique lo siguiente en **Escribir una expresión regular** :
    
      - En **Hacer coincidir este patrón**, especifique el patrón que se usará para hacer coincidir los números objeto de la conversión.
    
      - En **Regla de conversión**, especifique un patrón para el formato de los números convertidos.
    
    Por ejemplo, si especifica **^\\+(\\d{9}\\d+)$** en **Hacer coincidir este patrón** y **011$1** en **Regla de conversión**, la regla convertirá +441235551010 a 011441235551010.

8.  Haga clic en **Aceptar** para guardar la regla de conversión.

9.  Haga clic en **Aceptar** para guardar la configuración de tronco.

10. En la página **Configuración de tronco**, haga clic en **Confirmar** y, a continuación, en **Confirmar todo**.
    

    > [!NOTE]
    > Siempre que cree o modifique una regla de conversión, debe ejecutar el comando <STRONG>Confirmar todo</STRONG> para publicar el cambio en la configuración. Para obtener más información, vea <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publicar los cambios pendientes en la configuración del enrutamiento de voz en Lync Server 2013</A> en la documentación referente a las operaciones.



## Vea también

#### Tareas

[Crear o modificar una regla de conversión mediante la herramienta Generar una regla de conversión](lync-server-2013-create-or-modify-a-translation-rule-by-using-the-build-a-translation-rule-tool.md)  
[Configurar un tronco con omisión de medios en Lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md)  
[Configurar un tronco sin omisión de medios en Lync Server 2013](lync-server-2013-configure-a-trunk-without-media-bypass.md)  
[Publicar los cambios pendientes en la configuración del enrutamiento de voz en Lync Server 2013](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  

#### Conceptos

[Opciones globales de desvío de medios en Lync Server 2013](lync-server-2013-global-media-bypass-options.md)

