---
title: 'Lync Server 2013: crear o editar la configuración del asociado XMPP'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or edit XMPP partner configuration
ms:assetid: 362dbe5e-8ee9-4aba-8c26-5907312b4a60
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552447(v=OCS.15)
ms:contentKeyID: 48679558
ms.date: 09/03/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4410444d1565e61fa80ef8b8db29aad63b4401de
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42032496"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-edit-xmpp-partner-configuration-in-lync-server-2013"></a>Crear o editar la configuración del socio XMPP en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2014-09-03_

Microsoft Lync Server 2013 integra un proxy de protocolo extensible de mensajería y presencia (XMPP) en el servidor perimetral y una puerta de enlace XMPP en el servidor front-end o en el grupo de servidores front-end. Para permitir conexiones de otras implementaciones de XMPP, debe configurar XMPP en el panel de control de Lync Server. Las opciones de configuración se configuran por cada dominio XMPP. Para crear una nueva asociación de socio, lleve a cabo lo siguiente:

<div>

## <a name="to-create-a-new-federated-partner-or-edit-an-existing-configuration"></a>Para crear un nuevo socio federado o editar una configuración existente

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Acceso externo y de federación** y, a continuación, haga clic en **Socios federados XMPP**.

4.  Para crear una nueva configuración, haga clic en **Nuevo**.

5.  Para editar una configuración existente, seleccione la configuración y haga clic en **Editar**

6.  Para crear o editar configuraciones de **Socios federados XMPP**, defina las opciones siguientes:

7.  **Dominio principal** (obligatorio). El dominio principal es el dominio base del socio XMPP. Por ejemplo, escriba **fabrikam.com** en el nombre de dominio del socio XMPP. Esta es una entrada obligatoria.

8.  **Descripción**. La descripción es para las notas u otra información de identificación de esta configuración determinada. Este campo es opcional.

9.  **Dominios adicionales**. Son dominios que forman parte del dominio del socio de XMPP que debe incluirse como parte de la comunicación de XMPP permitida. Por ejemplo, si el dominio principal es **fabrikam.com**, debe incluir todos los demás dominios que se encuentren en fabrikam.com y con los que desee comunicarse mediante XMPP. Por ejemplo, puede especificar **corp.fabrikam.com** e **it.fabrikam.com** para el dominio XMPP corporativo y el dominio de tecnologías de información XMPP en el dominio XMPP principal de fabrikam.com.

10. **Tipo de socio**. El **Tipo de socio** es un valor obligatorio que ofrece una selección de tres opciones en un menú desplegable. Debe seleccionar una de las opciones siguientes para describir y aplicar el tipo de contacto que pueden agregarse. Puede seleccionar entre:
    
      - **Federado**. Un tipo de socio **federado** es una conexión de confianza entre una implementación de un socio de Lync Server o de Office Communications Server 2007 R2.
    
      - **Comprobaciones públicas**. Los socios son del tipo **público comprobado** cuando los contactos que forman parte de una implementación comprobada por el proveedor pueden agregarse a su lista de contactos. Las invitaciones se pueden enviar desde el usuario de Lync o el usuario de Lync puede aceptar invitaciones del contacto del asociado.
    
      - No se ha **comprobado el público**. Una relación **pública no comprobada** implica que no hay ningún estado establecido comprobable entre las dos implementaciones. Un usuario de Lync debe invitar al contacto sin verificar para que el contacto pueda agregar el usuario de Lync a su lista de contactos. Por ejemplo, Google GTalk no es un servicio XMPP de comprobación pública en relación con Lync Server. Un usuario de GTalk no podrá agregar el usuario de Lync como un contacto a menos que haya una invitación explícita enviada por el usuario de Lync.

11. Notas sobre la negociación de flujo y los métodos de seguridad Seguridad de la capa de transporte (TLS) y Autenticación de software y capa de seguridad (SASL):
    
    **XMPP Standards Foundation** (XSF) e **Internet Engineering Task Force** (IETF) definen un conjunto de reglas y estándares para el uso y la administración de certificados de clientes TLS, certificados de servidores TLS y del mecanismo SASL. La utilización de TLS y SASL es un proceso obligatorio para la protección del flujo XMPP. El documento de estándares XMPP **XEP-0178**, “especifica un flujo de protocolo recomendado para el uso del mecanismo SASL EXTERNO con certificados PKIX, sobre todo cuando un servicio XMPP indica que TLS es de negociación obligatoria.” PKIX, tal como indica la documentación de XSF, se refiere a la infraestructura de claves públicas, también conocida como PKI.
    
    Consulte el documento XEP-0178 de XSF para obtener más información sobre los requisitos de XMPP. Para obtener información detallada, consulte “XEP-0178: Procedimientos recomendados para el uso de SASL EXTERNO con certificados”. <http://xmpp.org/extensions/xep-0178.html>
    
    Consulte el documento IETF "extensible Messaging and Presence Protocol (XMPP): Core", sección 5,0, negociación <http://tools.ietf.org/html/rfc6120>de STARTTLS.
    
      - **Negociación TLS**. Define las reglas de negociación de TLS. Un servicio de XMPP puede requerir TLS, determinar que TLS es opcional o definir que TLS no se admite. Si se opta por la posibilidad opcional, es el servicio de XMPP quien decide si la negociación es obligatoria. Para ver todos los valores y detalles posibles para la negociación de SASL, TLS y devolución, incluidas las configuraciones de error conocidas y no válidas, vea [configuración de la negociación para socios federados XMPP en Lync Server 2013](lync-server-2013-negotiation-settings-for-xmpp-federated-partners.md).
        
          - <span></span>  
            **Es obligatorio**. El servicio de XMPP requiere la negociación TLS.
        
          - <span></span>  
            **Opcional**. El servicio de XMPP determina que TLS es de negociación obligatoria.
        
          - <span></span>  
            **No se admite**. El servicio de XMPP no admite TLS.
    
      - **Negociación SASL**. Define las reglas de negociación de SASL. Un servicio de XMPP puede requerir SASL, determinar que SASL sea opcional o definir que SASL no se admite. Si se selecciona la opción Opcional, será el servicio XMPP del socio el que tendrá que tomar una decisión de negociación obligatoria.
        
        <div>
        

        > [!WARNING]  
        > SASL requiere TLS. Para utilizar SASL, TLS debe ser obligatorio u opcional. Cualquier configuración que defina SASL como obligatorio u opcional debe ser compatible con TLS. Al hacer clic en <STRONG>Confirmar</STRONG> para guardar los cambios, si no ha establecido TLS como obligatorio u opcional, se mostrará una advertencia que indica que SASL debe ser compatible con TLS y que los cambios no se han guardado. Para resolver el error, establezca TLS como <STRONG>Obligatorio</STRONG> u <STRONG>Opcional</STRONG>. Si el uso de SASL es opcional y la negociación TLS no es posible, deberá establecer la negociación SASL como <STRONG>No compatible</STRONG>. Confirme con el servicio XMPP que los flujos de negociación adecuados deben ser para TLS y SASL o se producirá una interrupción en el servicio.

        
        </div>
        
          - <span></span>  
            **Es obligatorio**. El servicio de XMPP requiere la negociación SASL.
        
          - <span></span>  
            **Opcional**. El servicio de XMPP determina que SASL es de negociación obligatoria.
        
          - <span></span>  
            **No se admite**. El servicio de XMPP no admite SASL.
    
      - **Negociación de devolución**. La devolución negociación se define mediante el XSF en el documento **XEP-220: Server devolución** <http://xmpp.org/extensions/xep-0220.html>. El proceso de devolución de llamada del servidor usa el sistema de nombres de dominio (DNS) y un servidor relevante para comprobar que la solicitud procedía de un socio XMPP válido. Para ello, el servidor de origen crea un mensaje específico con una clave de devolución de llamada generada y busca el servidor de recepción en el DNS. El servidor de origen envía la clave en un flujo XML al resultado de la búsqueda de DNS, en principio, el servidor destinatario. A recibir la clave por el flujo XML, el servidor destinatario no responde al servidor de origen, sino que envía la clave a un servidor de autorización conocido. Este verifica que la validez de la clave. Si no lo es, el servidor destinatario no responde al servidor de origen. Si lo es, el servidor destinatario informa al servidor de origen de que la identidad y la clave son válidas, y la conversación puede iniciarse.
        
        Existen dos estados válidos en la **negociación de rellamada**:
        
          - <span></span>  
            **True**. El servidor XMPP está configurado para usar la negociación de devolución de llamada si se recibe una solicitud de un servidor de origen.
        
          - <span></span>  
            **Falso**. El servidor XMPP no está configurado para usar la negociación de devolución de llamada y si se recibe una solicitud de un servidor de origen, esta se ignorará.

</div>

</div>

<span> </span>

</div>

</div>

</div>

