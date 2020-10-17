---
title: 'Lync Server 2013: configurar certificados en el servidor que ejecuta la mensajería unificada de Microsoft Exchange Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure certificates on the server running Microsoft Exchange Server Unified Messaging
ms:assetid: 74c883b4-cef6-41a9-b2eb-7212be32fea4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398564(v=OCS.15)
ms:contentKeyID: 48184521
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 790798835694fcd76a4501c4b94e6ca59f220524
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48521047"
---
# <a name="configure-certificates-on-the-server-running-microsoft-exchange-server-unified-messaging"></a>Configurar certificados en el servidor que ejecuta la mensajería unificada de Microsoft Exchange Server

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-26_

Si ha implementado la mensajería unificada (MU) de Exchange, tal como se describe en [Planning for Exchange Unified Messaging Integration in Lync Server 2013](lync-server-2013-planning-for-exchange-unified-messaging-integration.md) en la documentación referente a la planeación y desea proporcionar características de MU de Exchange a los usuarios de Enterprise Voice de su organización, puede usar los siguientes procedimientos para configurar el certificado en el servidor que ejecuta la mensajería unificada de Exchange.

<div>


> [!IMPORTANT]  
> Para los certificados internos, tanto los servidores que ejecutan Lync Server 2013 como los servidores que ejecutan Microsoft Exchange deben tener certificados de entidades de certificación raíz de confianza que sean de confianza mutua. La entidad de certificación (CA) puede ser la misma o una entidad de certificación diferente, siempre que los servidores tengan el certificado raíz de la entidad de certificación registrado en su almacén de certificados de entidad de certificación raíz de confianza.



</div>

El servidor de Exchange debe estar configurado con un certificado de servidor para poder conectarse a Lync Server 2013:

1.  Descargue el certificado de la entidad de certificación para el servidor de Exchange.

2.  Instale el certificado de CA para el servidor de Exchange.

3.  Compruebe que la entidad de certificación se encuentra en la lista de entidades de certificación raíz de confianza del servidor de Exchange.

4.  Cree una solicitud de certificado para el servidor de Exchange e instale el certificado.

5.  Asigne el certificado para el servidor de Exchange.

<div>

## <a name="to-download-the-ca-certificate"></a>Para descargar el certificado de la entidad de certificación

1.  En el servidor que ejecuta la mensajería unificada de Exchange, haga clic en **Inicio**, en **ejecutar**, escriba **http:// \<name of your Issuing CA Server\> /CertSrv**y, a continuación, haga clic en **Aceptar**.

2.  En **Seleccione una tarea**, haga clic en **Descargar certificado de CA, cadena de certificados o CRL**.

3.  En **Descargar certificado de CA, cadena de certificados o CRL**, seleccione el **método de codificación para base 64**y, a continuación, haga clic en **Descargar certificado de CA**.
    
    <div>
    

    > [!NOTE]  
    > También puede especificar la codificación de las reglas de codificación distintiva (DER) en este paso. Si selecciona codificación en DER, el tipo de archivo en el siguiente paso de este procedimiento y en el paso 10 de <STRONG>para instalar el certificado de CA</STRONG> es. p7b en lugar de. cer.

    
    </div>

4.  En el cuadro de diálogo **descarga de archivos** , haga clic en **Guardar**y, a continuación, guarde el archivo en el disco duro del servidor. (El archivo tendrá una extensión de archivo. cer o. p7b, en función de la codificación que haya seleccionado en el paso anterior).

</div>

<div>

## <a name="to-install-the-ca-certificate"></a>Para instalar el certificado de la entidad de certificación

1.  En el servidor que ejecuta la mensajería unificada de Exchange, abra Microsoft Management Console (MMC); para ello, haga clic en **Inicio**, en **Ejecutar**, escriba **MMC** en el cuadro **abrir** y, a continuación, haga clic en **Aceptar**.

2.  En el menú **Archivo**, haga clic en **Agregar o quitar complemento** y, a continuación, en **Agregar**.

3.  En el cuadro **Agregar complementos independientes**, haga clic en **Certificados** y, a continuación, en **Agregar**.

4.  En el cuadro de diálogo **Complemento de certificados**, haga clic en **Cuenta de equipo** y, a continuación, haga clic en **Siguiente**.

5.  En el cuadro de diálogo **seleccionar equipo** , compruebe que la casilla **equipo local: (el equipo en el que se está ejecutando esta consola)** esté activada y, a continuación, haga clic en **Finalizar**.

6.  Haga clic en **Cerrar** y en **Aceptar**.

7.  En el árbol de la consola, expanda **certificados (equipo local)**, expanda **entidades de certificación raíz de confianza**y, a continuación, haga clic en **certificados**.

8.  Haga clic con el botón secundario en **certificados**, haga clic en **todas las tareas**y en **importar**.

9.  Haga clic en **Siguiente**.

10. Haga clic en **examinar** para buscar el archivo y, a continuación, haga clic en **siguiente**. (El archivo tendrá una extensión de archivo. cer o. p7b, en función de la codificación que haya seleccionado en el paso 3 de **para descargar el certificado de la entidad de certificación**.

11. Haga clic en **poner todos los certificados en el siguiente almacén**.

12. Haga clic en **examinar**y seleccione **entidades de certificación raíz de confianza**.

13. Haga clic en **siguiente** para comprobar la configuración y, a continuación, haga clic en **Finalizar**.

</div>

<div>

## <a name="to-verify-that-the-ca-is-in-the-list-of-trusted-root-cas"></a>Para comprobar que la entidad de certificación está en la lista de entidades de certificación raíz de confianza

1.  En el servidor que ejecuta la mensajería unificada de Exchange, en MMC expanda **certificados (equipo local)**, expanda **entidades de certificación raíz de confianza**y, a continuación, haga clic en **certificados**.

2.  En el panel de detalles, compruebe que la entidad de certificación se encuentra en la lista de entidades de certificación de confianza.

</div>

<div>

## <a name="to-configure-exchange-server-2013-um-with-lync-server"></a>Para configurar la mensajería unificada de Exchange Server 2013 con Lync Server

1.  Para obtener más información, consulte "integrar la mensajería unificada de Exchange 2013 con Lync Server" en la documentación de Exchange Server en [https://go.microsoft.com/fwlink/p/?LinkId=265372](https://go.microsoft.com/fwlink/p/?linkid=265372) .

</div>

<div>

## <a name="to-create-a-certificate-request-and-install-the-certificate-on-exchange-server-2007-sp1"></a>Para crear una solicitud de certificado e instalar el certificado en Exchange Server 2007 (SP1)

1.  En el servidor que ejecuta la mensajería unificada de Exchange, haga clic en **Inicio**, en **ejecutar**, escriba **http:// \<**name of your Issuing CA Server**\> /CertSrv**y, a continuación, haga clic en **Aceptar**.

2.  En **Seleccione una tarea**, haga clic en **solicitar un certificado**.

3.  En **solicitar un certificado**, haga clic en **solicitud de certificado avanzada**.

4.  En **solicitud de certificado avanzada**, haga clic en **crear y enviar una solicitud a esta CA**.

5.  En **solicitud de certificado avanzada**, seleccione **servidor Web** u otra plantilla de certificado de servidor configurada para la autenticación de servidor.

6.  En **identificar información para plantillas sin conexión**, en el cuadro **nombre** , escriba el nombre de dominio completo (FQDN) del servidor de Exchange.
    
    <div>
    

    > [!NOTE]  
    > Debe escribir el FQDN del servidor de Exchange para que las comunicaciones funcionen.

    
    </div>

7.  En **Opciones de clave**, active la casilla **de verificación almacenar el certificado en el almacén de certificados del equipo local** .

8.  Haga clic en el botón **Enviar** situado en la parte inferior de la Página Web.

9.  En el cuadro de diálogo que se abre solicitando confirmación, haga clic en **sí**.

10. En la página certificado emitido, en **certificado emitido**, haga clic en **instalar este certificado**.

11. En el cuadro de diálogo que se abre solicitando confirmación, haga clic en **sí**.

12. Compruebe que aparece el mensaje "el nuevo certificado se ha instalado correctamente".

</div>

<div>

## <a name="to-create-a-certificate-on-exchange-server-2010"></a>Para crear un certificado en Exchange Server 2010

1.  Inicie sesión en el servidor que ejecuta la mensajería unificada de Exchange con los derechos de usuario adecuados. Para obtener más información, consulte "Client Access Permissions" en [https://go.microsoft.com/fwlink/p/?linkId=195499](https://go.microsoft.com/fwlink/p/?linkid=195499) .

2.  Consulte los siguientes procedimientos para crear el certificado:
    
    1.  "Crear un nuevo certificado de Exchange" en [https://go.microsoft.com/fwlink/p/?linkId=195494](https://go.microsoft.com/fwlink/p/?linkid=195494)
    
    2.  "Importar un certificado de Exchange" en [https://go.microsoft.com/fwlink/p/?linkId=195496](https://go.microsoft.com/fwlink/p/?linkid=195496)
    
    <div>
    

    > [!NOTE]  
    > Para el <STRONG>nombre de sujeto</STRONG>del certificado, debe especificar el FQDN del servidor de Exchange para que las comunicaciones funcionen.

    
    </div>

</div>

<div>

## <a name="to-assign-the-certificate-on-exchange-server-2007-sp1"></a>Para asignar el certificado en Exchange Server 2007 (SP1)

1.  En el servidor que ejecuta la mensajería unificada de Exchange, abra MMC.

2.  En el árbol de la consola, expanda **personal** y, a continuación, haga clic en **certificados**.

3.  En el panel de detalles, compruebe que se muestra el certificado personal.

4.  Haga doble clic en el certificado para leer sus detalles y comprobar que es válido.
    
    <div>
    

    > [!NOTE]  
    > El certificado puede tardar unos minutos en mostrarse como válido.

    
    </div>

5.  Reinicie el servicio de mensajería unificada de Microsoft Exchange.
    
    <div>
    

    > [!NOTE]  
    > El servidor que ejecuta la mensajería unificada de Exchange Server 2007 SP1 recupera automáticamente el certificado correcto.

    
    </div>

6.  Abra el visor de eventos y busque el identificador de evento 1112, que especifica qué certificado ha recuperado el servidor que ejecuta la mensajería unificada de Exchange Server 2007 SP1.

</div>

<div>

## <a name="to-assign-the-certificate-on-exchange-server-2010"></a>Para asignar el certificado en Exchange Server 2010

1.  Inicie sesión en el servidor que ejecuta la mensajería unificada de Exchange con los derechos de usuario adecuados. Para obtener más información, consulte "Client Access Permissions" en [https://go.microsoft.com/fwlink/p/?linkId=195499](https://go.microsoft.com/fwlink/p/?linkid=195499) .

2.  Para obtener el procedimiento para asignar el certificado, consulte "asignar servicios a un certificado" en [https://go.microsoft.com/fwlink/p/?linkId=195497](https://go.microsoft.com/fwlink/p/?linkid=195497) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

