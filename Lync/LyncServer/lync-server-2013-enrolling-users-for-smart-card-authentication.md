---
title: 'Lync Server 2013: inscribir usuarios para la autenticación de tarjetas inteligentes'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Enrolling users for smart card authentication
ms:assetid: a6445a83-a94b-423f-ba2a-12b5f84c5d75
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn308570(v=OCS.15)
ms:contentKeyID: 54973691
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 11e74f35119a083aacd8440aec53594b8091b8e8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34835210"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enrolling-users-for-smart-card-authentication-in-lync-server-2013"></a>Inscribir usuarios para la autenticación de tarjetas inteligentes en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-07-03_

En general, existen dos métodos para inscribir a los usuarios en la autenticación de tarjeta inteligente. El método más sencillo consiste en que los usuarios se inscriban directamente en la autenticación de tarjeta inteligente a través de la inscripción web; el más complejo consiste en usar un Enrollment Agent. Este tema se centra en la autoinscripción para usar certificados de tarjeta inteligente.

Para obtener más información sobre la inscripción en nombre de los usuarios como agente de inscripción, consulte inscribirse para certificados en nombre de otros usuarios [http://go.microsoft.com/fwlink/p/?LinkID=313367](http://go.microsoft.com/fwlink/p/?linkid=313367)en.

<div>

## <a name="to-enroll-users-for-smart-card-authentication"></a>Para inscribir a usuarios en la autenticación de tarjeta inteligente

1.  Inicie sesión en la estación de trabajo Windows 8 con las credenciales de un usuario habilitado para Lync.

2.  Inicie Internet Explorer.

3.  Vaya a la página de **inscripción Web** de la entidad emisora de certificados (por ejemplo,. https://MyCA.contoso.com/certsrv)
    
    <div>
    

    > [!NOTE]  
    > Si usa Internet Explorer 10, puede que tenga que ver este sitio web en modo de compatibilidad.

    
    </div>

4.  En la página **principal**, elija **Solicitar un certificado**.

5.  Luego elija **Solicitud avanzada**.

6.  Elija **Crear y enviar una solicitud a esta CA**.

7.  Seleccione **Usuario de tarjeta inteligente** en la sección **Plantilla de certificado** y complete la solicitud de certificado avanzada con los siguientes valores:
    
      - En **Opciones de clave**, confirme la siguiente configuración:
        
          - Active el botón de radio **Crear conjunto de claves nuevo**.
        
          - En **CSP**, seleccione **Proveedor base de cifrado para tarjetas inteligentes de Microsoft**.
        
          - En **Uso de la clave**, seleccione **Exchange** (es la única opción disponible).
        
          - En **Tamaño de la clave**, escriba **2048**.
        
          - Confirme que está activado **Nombre automático de contenedor de claves**.
        
          - Deje las demás casillas desactivadas.
    
      - En **Opciones adicionales**, confirme los siguientes valores:
        
          - En **Formato de la solicitud**, seleccione **CMC**.
        
          - En **Algoritmo hash**, seleccione **sha1**.
        
          - En **Nombre descriptivo**, escriba **Smardcard Certificate**.

8.  Si utiliza un lector de tarjetas inteligentes físico, inserte la tarjeta inteligente en el dispositivo.

9.  Haga clic en **Enviar** para enviar la solicitud de certificado.

10. Cuando se le pida, escriba el PIN que se usó para crear la tarjeta inteligente virtual.
    
    <div>
    

    > [!NOTE]  
    > El valor del PIN de tarjeta inteligente virtual predeterminado es “12345678”.

    
    </div>

11. Una vez emitido el certificado, haga clic en **Instalar este certificado** para completar el proceso de inscripción.
    
    <div>
    

    > [!NOTE]  
    > Si la solicitud de certificado presenta el error “Este explorador web no es compatible con la creación de solicitudes de certificados”, hay tres formas de resolver el problema: 
    > <OL>
    > <LI>
    > <P>Habilitar la Vista de compatibilidad en Internet Explorer</P>
    > <LI>
    > <P>Habilitar la opción Activar configuración de Intranet en Internet Explorer</P>
    > <LI>
    > <P>Activar la opción Restablecer todas las zonas al nivel predeterminado en la pestaña Seguridad del menú de opciones de Internet Explorer.</P></LI></OL>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

