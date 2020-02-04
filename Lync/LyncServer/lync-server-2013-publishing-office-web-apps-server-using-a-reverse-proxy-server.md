---
title: Publicación de Office Web Apps Server con un servidor proxy inverso
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Publishing Office Web Apps Server using a reverse proxy server
ms:assetid: 0babe39f-c4b9-46f0-995a-33dc99c2be03
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204665(v=OCS.15)
ms:contentKeyID: 48183384
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 43a81fff75adbeadb6cfcead3316dab2c89b4269
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41724590"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="publishing-office-web-apps-server-in-lync-server-2013-using-a-reverse-proxy-server"></a>Publicación de Office Web Apps Server en Lync Server 2013 con un servidor proxy inverso

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-25_

Si quiere que los usuarios externos (es decir, los usuarios que inician sesión desde fuera del firewall de su organización) tengan acceso a las presentaciones de PowerPoint de Office Web Apps Server, tendrá que usar Office Web Apps Server y un servidor proxy inverso, como Microsoft Forefront Threat Management Gateway. Eso también significa que necesitará crear y configurar una regla de publicación de sitios web; esa regla le ayudará a garantizar que los usuarios puedan conectarse al servidor. Si no necesita proporcionar acceso a usuarios externos, no necesita configurar una regla de publicación de sitios Web.

Para configurar una regla de publicación de sitios web en Forefront Threat Management Gateway, complete el siguiente procedimiento:

1.  Haga clic en **Inicio**, haga clic en **todos los programas**, **Microsoft Forefront TMG**y, a continuación, haga clic en **Administración de Forefront TMG**.

2.  En Forefront TMG, haga clic con el botón derecho en **Directiva de Firewall**, seleccione **nuevo**y, a continuación, haga clic en regla de **publicación de sitio web**.

3.  En el Asistente para nueva regla de publicación de Web, en la página asistente **para nueva regla de publicación de web** , escriba un nombre para la nueva regla en el cuadro Nombre de la **regla de publicación de web** (por ejemplo, regla de **Office Web Apps Server**) y, a continuación, haga clic en **siguiente**.

4.  En la página **especificar acción de regla** , seleccione **permitir** y, a continuación, haga clic en **siguiente**.

5.  En la página **tipo de publicación** , seleccione **publicar un único sitio web o equilibrador de carga** y, a continuación, haga clic en **siguiente**.

6.  En la página **seguridad de conexión de servidor** , seleccione **usar SSL para conectarse al servidor web o conjunto** de servidores publicado y, a continuación, haga clic en **siguiente**.

7.  En la página **Internal Publishing details** , escriba el FQDN de su servidor de Office Web Apps (por ejemplo, **officewebapps01.contoso.com**) en el cuadro **nombre de sitio interno** y, a continuación, haga clic en **siguiente**. El nombre introducido en el cuadro **nombre de sitio interno** debe aparecer en el campo de asunto o en el campo de nombre alternativo de asunto del certificado que haya asignado a Office Web Apps Server.

8.  En la página **Internal Publishing details** , escriba ** / ** la ruta de **acceso (opcional)** y, a continuación, haga clic en **Next**. La sintaxis\* /ayuda a garantizar que todas las carpetas y subcarpetas del sitio estén publicadas.

9.  En la página **detalles de nombre público** , seleccione **este nombre de dominio (escriba a continuación)** en la lista desplegable **aceptar solicitudes de** y, a continuación, escriba el nombre completo de su servidor de Office Web Apps en el cuadro Nombre público. Este nombre debe ser el nombre usado para acceder a su sitio Web. Por ejemplo, si se obtiene acceso a su sitio con la http://officewebapps01.contoso.com dirección URL, debe escribir **officewebapps01.contoso.com** en el cuadro **nombre público** .

10. Haga clic en **Siguiente**.

11. En la página **seleccionar escucha de web** , haga clic en **nuevo**.

12. En el Asistente para nueva definición de escucha de Web, escriba un nombre para la nueva escucha de Web (por ejemplo, **SSL**) en el cuadro Nombre de la **escucha de web** y, a continuación, haga clic en **siguiente**.

13. En la página **seguridad de conexión de cliente** , seleccione **requerir conexiones seguras SSL con los clientes** y, a continuación, haga clic en **siguiente**.

14. En la página **direcciones IP de escucha de web** , seleccione **externo**, seleccione **interno**y, a continuación, haga clic en **siguiente**.

15. En la página **certificados SSL de escucha** , seleccione **usar un único certificado para esta escucha de web** y, a continuación, haga clic en **seleccionar certificado**.

16. En el cuadro de diálogo **seleccionar certificado** , seleccione el certificado que se usará para esta escucha de web y, a continuación, haga clic en **seleccionar**.

17. En la página **certificados SSL de escucha** , haga clic en **siguiente**.

18. En la **página Configuración de autenticación** , seleccione **sin autenticación** en la lista desplegable **Seleccione cómo los clientes proporcionarán las credenciales a Forefront TMG** y, a continuación, haga clic en **siguiente**.

19. En la página **configuración de inicio de sesión único** , haga clic en **siguiente**.

20. En la página **finalización del Asistente para nueva escucha de web** , revise el Resumen de las opciones de configuración que ha realizado. Cuando esté listo, haga clic en **Finalizar**.

21. En la página **seleccionar escucha de web** , haga clic en **siguiente**.

22. En la página **delegación de autenticación** , seleccione **sin delegación, pero el cliente puede autenticar directamente** desde el **Seleccione el método usado por Forefront TMG para autenticarse en la lista desplegable servidor Web publicado** y, a continuación, haga clic en **siguiente**.

23. En la página **conjuntos de usuarios** , confirme que aparecen los conjuntos de usuarios adecuados. De forma predeterminada, este es el conjunto de usuarios de **todos los usuarios** . Haga clic en **Agregar** para agregar otros conjuntos de usuarios que haya definido. Cuando haya terminado, haga clic en **siguiente**.

24. En la página **finalización del Asistente para nueva regla de publicación de web** , haga clic en **Finalizar**.

Tenga en cuenta que hacer clic en **Finalizar** no significa que haya completado el proceso; es decir, esto no aplica automáticamente y habilita la nueva regla. En su lugar, tendrá que hacer clic en el botón **aplicar** que aparecerá en la interfaz de usuario de Forefront TMG. Al hacer clic en **aplicar** el cuadro de diálogo **Descripción de cambio de configuración** aparecerá. Haga clic en **aplicar** en ese cuadro de diálogo para habilitar la nueva regla de publicación.

Una vez que se haya aplicado la nueva regla, tendrá que realizar algunas modificaciones menores en la regla para asegurarse de que los usuarios pueden usar las nuevas capacidades de presentación de PowerPoint. Para ello, realice el procedimiento siguiente:

1.  En Forefront TMG, haga clic con el botón secundario en el nombre de la nueva regla de publicación y, a continuación, haga clic en **propiedades**.

2.  En el cuadro de diálogo **propiedades** , en la pestaña **para** , seleccione la opción **reenviar el encabezado de host original en lugar del real**.

3.  En la pestaña **tráfico** , haga clic en **filtrado** y, a continuación, haga clic en **configurar http**.

4.  En el cuadro de diálogo **configurar directiva http para la regla** , desactive la casilla **comprobar normalización** y haga clic en **Aceptar**.

5.  En el cuadro de diálogo **propiedades** , haga clic en **Aceptar**.

6.  En Forefront TMG, haga clic en **aplicar** para habilitar los cambios. Cuando aparezca el cuadro de diálogo **Descripción de cambio de configuración** , haga clic en **aplicar**.

Después de completar la instalación, puede probar su servidor de Office Web Apps con los procedimientos del tema [validar la configuración de Office Web Apps Server en Lync server 2013](lync-server-2013-validating-the-configuration-of-office-web-apps-server.md).

</div>

<span> </span>

</div>

</div>

</div>

