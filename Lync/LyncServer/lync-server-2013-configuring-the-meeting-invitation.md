---
title: Configuración de la invitación a reunión en Lync Server 2013
TOCTitle: Configuración de la invitación a reunión en Lync Server 2013
ms:assetid: 7faa4797-0344-418b-9fa3-59dfb9c2baf7
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg398638(v=OCS.15)
ms:contentKeyID: 48275825
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuración de la invitación a reunión en Lync Server 2013

 

_**Última modificación del tema:** 2013-07-16_

Puede personalizar las invitaciones de la reunión enviadas por el Complemento para conferencia en línea para Lync 2013 al incluir los elementos opcionales en el cuerpo de la invitación a la reunión:

  - **El logotipo de la organización** Agregue el logotipo de su organización para las invitaciones de reuniones al usar la opción Dirección URL del logotipo. Si las invitaciones a la reunión se enviarán a las personas externas a su organización, la imagen deberá ubicarse en una dirección URL disponible de forma pública. Los formatos de imagen admitidos son GIF y JPG. Aunque Lync Server 2013 guarda la URL sin restricciones de imagen, para conseguir mejores resultados, el tamaño máximo de la imagen deberá ser de 30 píxeles de alto por 188 de ancho.

  - **Un vínculo de soporte o ayuda personalizada** Agregue una dirección URL para el sitio web de soporte o ayuda de su organización. Si las invitaciones a la reunión se enviaran a personas externas a su organización, la dirección URL deberá estar disponible de forma pública. La longitud máxima de la URL es de 1 KB.

  - **Texto de limitación de responsabilidad legal** Agregue una dirección URL para un texto legal o para una limitación de responsabilidad que se mostrará en todas las invitaciones a reuniones. Si las invitaciones a la reunión se enviaran a personas externas a su organización, la dirección URL deberá estar disponible de forma pública. La longitud máxima de la URL es de 1 KB..

  - **Texto personalizado del pie de página** Agregue texto que se mostrará como un pie de página personalizado en la invitación. La longitud máxima de texto que puede agregarse es de 2 KB.

Puede configurar estas opciones mediante el Panel de control de Lync Server o Shell de administración de Lync Server.


**Para personalizar la invitación a la reunión con Panel de control de Lync Server**

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tenga derechos de usuario equivalentes), o se asigne al rol CsServerAdministrator o CsAdministrator, inicie sesión en cualquier equipo que esté en la red en la que haya implementado Lync Server 2013.

2.  Abra una ventana del explorador y después introduzca la dirección URL de administración para abrir el panel de control de Lync Server. Para más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Abrir las herramientas administrativas de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Conferencia** y luego en **Configuración de reunión**.

4.  En la página **Configuración de reunión** haga clic en **Nuevo** y luego realice una de las siguientes acciones:
    
      - Para crear una política en el nivel del sitio, haga clic en **Configuración de sitio**. En el campo de búsqueda **Seleccionar un sitio**, escriba el nombre, o parte del nombre, del sitio para el que desea definir las opciones de configuración para unirse a reuniones. En la lista de sitios resultante, haga clic en el sitio que desee y luego haga clic en **Aceptar**.
    
      - Para crear una política en el nivel de grupo, haga clic en **Configuración de grupo**. En el campo de búsqueda **Seleccionar un servicio**, escriba el nombre, o parte del nombre, del sitio para el que desea definir las opciones de configuración para unirse a reuniones. En la lista de servicios resultante, haga clic en el grupo que desee y luego en **Aceptar**.

5.  Realice cualquiera de las siguientes acciones:
    
      - En el campo **Dirección URL del logotipo**, escriba la dirección URL de la imagen del logotipo de su organización.
    
      - En el campo **Dirección URL de la Ayuda**, escriba la dirección URL del sitio de soporte o ayuda de su organización.
    
      - En el campo **Texto legal**, escriba la dirección URL del texto legal o de la renuncia que desea incluir en las invitaciones a reuniones.
    
      - En el campo **Texto de pie de página personalizado**, escriba el texto del pie de página de hasta 2 KB.

**Para personalizar la invitación a reunión con Shell de administración de Lync Server**

1.  Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y, después, en **Shell de administración de Lync Server**.

2.  Ejecute el cmdlet **New-CsMeetingConfiguration** o **Set-CsMeetingConfiguration** para crear las opciones de invitación a reunión. Por ejemplo, ejecute:
    
        New-CsMeetingConfiguration -Identity site:Redmond -EnableInviteCustomization $True -LogoURL "http://www.contoso.com/logo/contosobanner.gif" -HelpURL "http://www.contoso.com/support" -LegalURL "http://www.contoso.com/disclaimer" -CustomFooterText "Communications may be monitored or recorded."

