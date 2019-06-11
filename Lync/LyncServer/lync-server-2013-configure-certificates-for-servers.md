---
title: 'Lync Server 2013: Configurar certificados para servidores'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure certificates for servers
ms:assetid: e12e59b5-a146-4859-86ec-cabfc198c7b5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398995(v=OCS.15)
ms:contentKeyID: 48185531
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 21a0e239074b4f6d4638214fad41ff8ba18078fc
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842427"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-certificates-for-servers-in-lync-server-2013"></a>Configurar certificados para servidores en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-03-17_

Para completar correctamente este procedimiento, debe haber iniciado sesión como un usuario que sea miembro del grupo RTCUniversalServerAdmins o tener los permisos configurados correctamente. Para obtener más información sobre la delegación de permisos, consulte [permisos de configuración de delegación en Lync Server 2013](lync-server-2013-delegate-setup-permissions.md). En función de su organización y de los requisitos para solicitar certificados, es posible que necesite otras pertenencias a grupos. Consulte con el grupo que administra la entidad de certificación (CA) de la infraestructura de clave pública (PKI).

<div>


> [!NOTE]  
> Lync Server 2013 incluye compatibilidad con el conjunto de algoritmos Sha-2 (SHA-2 y longitudes implícitas de 224, 256, 384 o 512 bits) de algoritmos hash y de firma de síntesis para conexiones de clientes que ejecutan Windows 7, Windows Server 2008 R2, Windows Server 2008, Windows Vista o Sistemas operativos Windows XP, además de Lync Phone Edition. Para permitir el acceso externo mediante el conjunto de aplicaciones SHA-2, el certificado externo lo emite una CA pública que también puede emitir un certificado con las mismas longitudes de bits de síntesis.



</div>

<div>


> [!WARNING]  
> La selección de la síntesis de hash y el algoritmo de firma depende de los clientes y de los servidores que usarán el certificado y de otros equipos y dispositivos con los que los clientes y servidores se comunicarán, quienes también deben saber cómo usar los algoritmos del certificado. Para obtener información sobre qué longitudes de compendio se admiten en el sistema operativo y en<A href="http://go.microsoft.com/fwlink/?linkid=287002">http://go.microsoft.com/fwlink/?LinkId=287002</A>algunas aplicaciones cliente, consulte.



</div>

Cada servidor Standard Edition o servidor front-end requiere hasta cuatro certificados: el certificado oAuthTokenIssuer, un certificado predeterminado, un certificado interno web y un certificado externo Web. Sin embargo, es posible solicitar y asignar un único certificado predeterminado con las entradas de nombre alternativo de asunto apropiados, así como el certificado oAuthTokenIssuer. Para obtener más información sobre los requisitos de certificado, consulte [requisitos de certificados para servidores internos en Lync Server 2013](lync-server-2013-certificate-requirements-for-internal-servers.md). Para obtener más información sobre cómo solicitar, asignar e instalar el certificado oAuthTokenIssuer, vea [administrar la autenticación de servidor a servidor (OAuth) y aplicaciones de Partners en Lync server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md)

Use el siguiente procedimiento para solicitar, asignar e instalar certificados de servidor Standard Edition o front-end. Repita el procedimiento para cada servidor front-end.

<div>


> [!IMPORTANT]  
> En el procedimiento siguiente se describe cómo configurar certificados de una PKI de empresa interna implementada por la organización y con procesamiento de solicitudes sin conexión. Para obtener información sobre cómo obtener certificados de una entidad de certificación pública, consulte <A href="lync-server-2013-certificate-requirements-for-internal-servers.md">requisitos de certificados para servidores internos en Lync Server 2013</A> en la documentación de planeación. Además, este procedimiento describe cómo solicitar, asignar e instalar certificados durante la configuración del servidor front-end. Si ha solicitado certificados por adelantado, como se describe en la sección <A href="lync-server-2013-request-certificates-in-advance-optional.md">solicitar certificados de antemano (opcional) para Lync Server 2013</A> de esta documentación de implementación, o si no usa una PKI de empresa interna implementada en su organización para obtener certificados, debe modificar este procedimiento según corresponda.



</div>

<div>

## <a name="to-configure-certificates-for-a-front-end-server"></a>Para configurar certificados para un servidor front-end

1.  En el Asistente para la implementación de Lync Server, haga clic en **Ejecutar** junto al **paso 3: solicitar, instalar o asignar certificados**.

2.  En la página **Asistente para certificados**, haga clic en **Solicitar**.

3.  En la página **solicitud de certificado** , haga clic en **siguiente**.

4.  En la página **Solicitudes retrasadas o inmediatas**, acepte la opción predeterminada **Envíe la solicitud inmediatamente a una entidad de certificación en línea** haciendo clic en **Siguiente**. La CA interna con inscripción en línea automática debe estar disponible si selecciona esta opción. Si elige la opción para retrasar la solicitud, se le pedirá un nombre y una ubicación para guardar el archivo de solicitud de certificado. La solicitud de certificado debe ser presentada y procesada por una CA de su organización o bien por una CA pública. Después, tendrá que importar la respuesta de certificado y asignarla al rol de certificado apropiado.

5.  En la página elegir una entidad emisora de **certificados (CA)** , seleccione la opción **seleccionar una CA de la lista detectada en su entorno** y, a continuación, seleccione una CA conocida (mediante registro en servicios de dominio de Active Directory) de la lista. O bien, seleccione la opción **Especificar otra entidad de certificación** escriba el nombre de otra CA en el cuadro y haga clic en **Siguiente**.

6.  En la página **Cuenta de la entidad de certificación**, se solicitan sus credenciales para solicitar y procesar la solicitud de certificado en la CA. Es necesario que haya determinado si es necesario un nombre de usuario y una contraseña para solicitar un certificado por adelantado. El administrador de la entidad emisora de certificados tendrá la información necesaria y es posible que tenga que ayudarle en este paso. Si tiene que especificar credenciales alternativas, active la casilla, escriba un nombre de usuario y una contraseña en los cuadros de texto y haga clic en **Siguiente**.

7.  En la página **Especificar plantilla de certificado alternativa**, haga clic en **Siguiente** para usar la plantilla de servidor web predeterminada.
    
    <div>
    

    > [!NOTE]  
    > Si su organización ha creado una plantilla para usar como alternativa a la plantilla de la CA de servidor web predeterminada, seleccione la casilla y escriba el nombre de la plantilla alternativa. Necesitará el nombre de la plantilla definido por el administrador de CA.

    
    </div>

8.  En la página **nombre y configuración de seguridad** , especifique un **nombre descriptivo** que le permita identificar el certificado y el propósito. Si deja el campo en blanco, se generará un nombre automáticamente. Establezca la **longitud de bit** de la tecla o acepte el valor predeterminado de 2048 bits. Seleccione la **clave privada del certificado como** exportable si determina que el certificado y la clave privada se deben mover o copiar a otros sistemas y, a continuación, haga clic en **siguiente**.
    
    <div>
    

    > [!NOTE]  
    > Lync Server 2013 tiene los requisitos mínimos para una clave privada exportable. Uno de estos sitios se encuentra en los servidores perimetrales en un grupo de servidores, donde el servicio de autenticación relé multimedia usa copias del certificado, en lugar de certificados individuales para cada instancia en el grupo de servidores.

    
    </div>

9.  En la página **Información de la organización**, si lo desea, proporcione información de la organización y después haga clic en **Siguiente**.

10. En la página **Información geográfica**, si lo desea, escriba información geográfica y después haga clic en **Siguiente**.

11. En la página **Nombre del sujeto/Nombres alternativos del juego**, revise los nombres alternativos del sujeto que se van a agregar y haga clic en **Siguiente**.

12. En la página **Configuración del dominio SIP**, active la casilla **Dominio SIP** y haga clic en **Siguiente**.

13. En la página **Configurar nombres alternativos de sujeto adicionales**, agregue los nombres alternativos de sujeto adicionales que desee, incluido cualquiera que piense que puede ser necesario para dominios SIP adicionales en el futuro, y haga clic en **Siguiente**.

14. En la página **Resumen de la solicitud de certificados**, revise la información del resumen. Si la información es correcta, haga clic en **Siguiente**. Si necesita corregir o modificar una configuración, haga clic en **Atrás** para ir a la página pertinente y realizar la corrección o modificación.

15. En la página **Ejecución de comandos**, haga clic en **Siguiente**.

16. On the **Online Certificate Request Status** page, review the information returned. You should note that the certificate was issued and installed into the local certificate store. Si se le informa de que ha sido emitido e instalado, pero no es válido, asegúrese de que el certificado raíz de la CA se ha instalado en el almacén de CA raíz de confianza del servidor. Refer to your CA documentation on how to retrieve a Trusted Root CA certificate. If you need to view the retrieved certificate, click **View Certificate Details**. De forma predeterminada, la casilla para **asignar el certificado a los usos del certificado de Lync Server** está activada. If you want to manually assign the certificate, clear the check box, and then click **Finish**.

17. Si desactivó la casilla para **asignar el certificado a los usos del certificado de Lync Server** en la página anterior, aparecerá la página asignación de **certificado** . Click **Next**.

18. En la página **Almacén de certificados**, seleccione el certificado solicitado. Si desea ver el certificado, haga clic en **Ver detalles del certificado** y en **Siguiente** para continuar.
    
    <div>
    

    > [!NOTE]  
    > Si la página de estado de la <STRONG>solicitud de certificado en línea</STRONG> notificó un problema con el certificado, como el certificado no es válido, la visualización del certificado real puede ayudar a resolver el problema. Dos problemas específicos que pueden hacer que un certificado no sea válido son que falte el certificado de la CA raíz de confianza mencionado anteriormente o que falte una clave privada asociada con el certificado. Consulte la documentación de la CA para resolver estos dos problemas.

    
    </div>

19. En la página **Resumen de asignación de certificados**, revise la información proporcionada para garantizar que este sea el certificado que debe asignarse y haga clic en **Siguiente**.

20. En la página **Ejecución de comandos**, revise el resultado del comando. Haga clic en **Ver registro** si desea revisar el proceso de asignación o si se ha emitido algún error o advertencia. Cuando termine, haga clic en **Finalizar**.

21. En la página **Asistente para certificados** , compruebe que el **Estado** del certificado es "asignado" y, a continuación, haga clic en **cerrar**.

</div>

<div>

## <a name="see-also"></a>Vea también


[Requisitos de la infraestructura de certificados para Lync Server 2013](lync-server-2013-certificate-infrastructure-requirements.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

