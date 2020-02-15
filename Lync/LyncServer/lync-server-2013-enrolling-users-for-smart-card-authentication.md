---
title: 'Lync Server 2013: inscripción de usuarios para la autenticación de tarjeta inteligente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enrolling users for smart card authentication
ms:assetid: a6445a83-a94b-423f-ba2a-12b5f84c5d75
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn308570(v=OCS.15)
ms:contentKeyID: 54973691
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a1d60a29eff876ef362d15c90e2615fd70bc8774
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2020
ms.locfileid: "41993815"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enrolling-users-for-smart-card-authentication-in-lync-server-2013"></a>Inscripción de usuarios para la autenticación de tarjeta inteligente en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-07-03_

Generalmente hay dos métodos para inscribir a los usuarios para la autenticación de tarjeta inteligente. El método más sencillo implica que los usuarios se inscriban directamente en la autenticación de tarjetas inteligentes mediante la inscripción Web, mientras que el método más complejo implica el uso de un agente de inscripción. Este tema se centra en la inscripción automática de certificados de tarjetas inteligentes.

Para obtener más información sobre la inscripción en nombre de usuarios como agente de inscripción, consulte inscribirse para certificados en nombre de otros usuarios en [http://go.microsoft.com/fwlink/p/?LinkID=313367](http://go.microsoft.com/fwlink/p/?linkid=313367).

<div>

## <a name="to-enroll-users-for-smart-card-authentication"></a>Para inscribir usuarios para la autenticación de tarjeta inteligente

1.  Inicie sesión en la estación de trabajo Windows 8 con las credenciales de un usuario habilitado para Lync.

2.  Inicie Internet Explorer.

3.  Vaya a la página de **inscripción Web** de la entidad de https://MyCA.contoso.com/certsrv)certificación (por ejemplo,.
    
    <div>
    

    > [!NOTE]  
    > Si usa Internet Explorer 10, es posible que deba ver este sitio web en modo de compatibilidad.

    
    </div>

4.  En la página **principal** , seleccione **solicitar un certificado**.

5.  A continuación, seleccione **solicitud avanzada**.

6.  Seleccione **crear y enviar una solicitud a esta CA**.

7.  Seleccione **usuario de tarjeta inteligente** en la sección **plantilla de certificado** y complete la solicitud de certificado avanzada con los siguientes valores:
    
      - **Las opciones de clave** confirman la siguiente configuración:
        
          - Seleccione el botón de opción **crear conjunto de claves nuevo**
        
          - Para **CSP**, seleccione **proveedor base de cifrado de tarjetas inteligentes de Microsoft**
        
          - En **uso**de la clave, seleccione **Exchange** (esta es la única opción disponible).
        
          - En **tamaño de clave**, escriba **2048**
        
          - Confirmar que **el nombre del contenedor de claves automático** está seleccionado
        
          - Deje las demás casillas desactivadas.
    
      - En **opciones adicionales** , confirme los siguientes valores:
        
          - En **formato de solicitud** , seleccione **CMC**.
        
          - Para el **algoritmo hash** , seleccione **SHA1**.
        
          - Para **nombre descriptivo** , escriba **Smardcard certificado**.

8.  Si usa un lector de tarjetas inteligentes físico, inserte la tarjeta inteligente en el dispositivo.

9.  Haga clic en **Enviar** para enviar la solicitud de certificado.

10. Cuando se le solicite, escriba el PIN que se usó para crear la tarjeta inteligente virtual.
    
    <div>
    

    > [!NOTE]  
    > El valor PIN predeterminado de la tarjeta inteligente virtual es "12345678".

    
    </div>

11. Una vez emitido el certificado, haga clic en **instalar este certificado** para completar el proceso de inscripción.
    
    <div>
    

    > [!NOTE]  
    > Si la solicitud de certificado produce el error "este explorador Web no admite la generación de solicitudes de certificado", hay tres formas posibles de resolver el problema: 
    > <OL>
    > <LI>
    > <P>Habilitar la vista de compatibilidad en Internet Explorer</P>
    > <LI>
    > <P>Habilitar la opción Activar configuración de intranet en Internet Explorer</P>
    > <LI>
    > <P>Seleccione la opción restablecer todas las zonas a nivel predeterminado en la ficha Seguridad en el menú opciones de Internet Explorer.</P></LI></OL>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

