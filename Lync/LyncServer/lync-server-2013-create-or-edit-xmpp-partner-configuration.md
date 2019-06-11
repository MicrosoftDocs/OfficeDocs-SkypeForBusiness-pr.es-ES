---
title: 'Lync Server 2013: Crear o editar la configuración de socios de XMPP'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create or edit XMPP partner configuration
ms:assetid: 362dbe5e-8ee9-4aba-8c26-5907312b4a60
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552447(v=OCS.15)
ms:contentKeyID: 48679558
ms.date: 09/03/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 488fa84a3f24133c6ebcde4467cacdbdcffe7ff8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34835836"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-edit-xmpp-partner-configuration-in-lync-server-2013"></a>Crear o editar la configuración de socios de XMPP en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2014-09-03_

Microsoft Lync Server 2013 integra un proxy de protocolo de presencia y mensajería extensible (XMPP) en el servidor perimetral y una puerta de enlace XMPP en el servidor front-end o en el grupo front-end. Para permitir conexiones de otras implementaciones de XMPP, debe configurar el XMPP en el panel de control de Lync Server. La configuración se establece en un dominio XMPP. Para crear una nueva asociación de socio, haga lo siguiente:

<div>

## <a name="to-create-a-new-federated-partner-or-edit-an-existing-configuration"></a>Para crear un nuevo socio federado o editar una configuración existente

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [abrir las herramientas administrativas 2013 de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Federación y acceso externo**y, a continuación, haga clic en los **socios de XMPP federados**.

4.  Para crear una configuración nueva, haga clic en **nuevo** .

5.  Para editar una configuración existente, seleccione la configuración y haga clic en **Editar** .

6.  Para crear o Editar configuraciones para los **socios de XMPP federados**, defina las siguientes opciones de configuración:

7.  **Dominio principal** (Obligatorio). El dominio principal es el dominio base del socio XMPP. Por ejemplo, tendría que escribir **fabrikam.com** para el nombre de dominio del socio XMPP. Esta es una entrada obligatoria.

8.  **Descripción**. La descripción es para notas u otra información que la identifique para esta configuración en particular. Esta entrada es opcional.

9.  **Dominios adicionales**. Los dominios adicionales son dominios que forman parte de su dominio del asociado XMPP y que deben incluirse como parte de la comunicación XMPP permitida. Por ejemplo, si el dominio principal es **fabrikam.com**, se mostrarán todos los demás dominios de fabrikam.com con los que se comunicará mediante XMPP. Por ejemplo, puede escribir **Corp.fabrikam.com** y **it.fabrikam.com** para el dominio de la empresa XMPP y el dominio XMPP de tecnologías de la información en el dominio XMPP principal de fabrikam.

10. **Tipo de socio**. El **tipo de socio** es un valor obligatorio y le ofrece una selección de tres opciones en un menú desplegable. Debe elegir una de las siguientes opciones para describir y exigir qué contactos se pueden agregar. Puede seleccionar:
    
      - **Federado**. Un tipo de socio **federado** es una conexión de confianza entre una implementación de un partner de Lync Server o de Office Communications Server 2007 R2.
    
      - **Verificado público**. Un socio **verificado público** es cuando los contactos que forman parte de una implementación verificada por el proveedor se pueden agregar a la lista de contactos del usuario. Las invitaciones pueden enviarse desde el usuario de Lync o el usuario de Lync puede aceptar invitaciones del contacto del socio.
    
      - No se ha comprobado el **público**. Una relación **pública** no verificada implica que no hay ningún estado verificado y comprobado entre las dos implementaciones. Un usuario de Lync debe invitar al contacto no verificado para que sea capaz de agregar el usuario de Lync a su lista de contactos. Por ejemplo, Google GTalk no es un servicio XMPP de comprobación pública, ya que se relaciona con Lync Server. Un usuario de GTalk no podrá agregar el usuario de Lync como contacto, a menos que haya una invitación explícita enviada por el usuario de Lync.

11. Notas sobre la negociación de secuencias y los métodos de seguridad seguridad de la capa de transporte (TLS) y nivel de seguridad y autenticación de software (SASL):
    
    Los **estándares XMPP Standard** (xsf) e **Internet Engineering Task Force** (IETF) definen un conjunto de reglas y estándares para usar y administrar certificados de cliente TLS, certificados de servidor TLS y el mecanismo SASL. El uso de TLS y SASL es el proceso necesario para proteger la secuencia XMPP. En el documento de normas XMPP **XEP-0178**, se especifica un flujo de protocolo recomendado para el uso del mecanismo externo SASL con certificados PKIX, especialmente cuando un servicio XMPP indica que TLS es obligatorio para negociar. PKIX, como se indica en la documentación de XSF, hace referencia a la infraestructura de claves públicas, también conocida como PKI.
    
    Para obtener más información sobre los requisitos del XMPP, consulte el documento XSF XEP-0178. Para obtener más información, consulte "XEP-0178: procedimientos recomendados para usar SASL externo con certificados". <http://xmpp.org/extensions/xep-0178.html>
    
    Consulte el documento IETF "Protocolo de presencia y mensajería extensible (XMPP): núcleo", sección 5,0, negociación <http://tools.ietf.org/html/rfc6120>STARTTLS.
    
      - **Negociación TLS**. Define las reglas de negociación de TLS. Un servicio XMPP puede requerir TLS, puede hacer que TLS sea opcional o usted define que no se admite la TLS. Si elige opcional, el requisito quedará en el servicio XMPP para una decisión obligatoria para la negociación. Para ver todas las configuraciones posibles y los detalles de la negociación SASL, TLS y Dialback, incluidas las configuraciones no válidas y de errores conocidos, vea [configuración de la negociación para socios de XMPP federados en Lync Server 2013](lync-server-2013-negotiation-settings-for-xmpp-federated-partners.md).
        
          - <span></span>  
            **Requerido**. El servicio XMPP requiere negociación TLS.
        
          - <span></span>  
            **Opcional**. El servicio XMPP indica que TLS es obligatorio para negociar.
        
          - <span></span>  
            **No es compatible**. El servicio XMPP no admite TLS.
    
      - **Negociación de SASL**. Define las reglas de negociación de SASL. Un servicio XMPP puede requerir SASL, puede hacer que SASL sea opcional o usted define que SASL no es compatible. Si elige opcional, el servicio XMPP del socio dejará de ser necesario para una decisión obligatoria para la negociación.
        
        <div>
        

        > [!WARNING]  
        > SASL requiere TLS. Para usar SASL, TLS debe ser obligatorio u opcional. Cualquier configuración que defina SASL como requerido u opcional debe tener compatibilidad con TLS. Al hacer clic en <STRONG>confirmar</STRONG> para guardar los cambios, si no ha establecido TLS en obligatorio u opcional, se le advertirá de que SASL debe tener compatibilidad con TLS y los cambios no se guardarán. Para resolver el error, establezca TLS en <STRONG></STRONG> required u <STRONG>Optional</STRONG>. Si el uso de SASL es opcional y la compatibilidad con la negociación TLS no es posible, debe establecer la negociación de SASL en <STRONG>no compatible</STRONG>. Confirmar con el servicio XMPP qué deben tener las secuencias de negociación apropiadas para TLS y SASL, o se producirá una interrupción del servicio.

        
        </div>
        
          - <span></span>  
            **Requerido**. El servicio XMPP requiere negociación SASL.
        
          - <span></span>  
            **Opcional**. El servicio XMPP indica que SASL es obligatorio para negociar.
        
          - <span></span>  
            **No es compatible**. El servicio XMPP no admite SASL.
    
      - **Negociación de Dialback**. El XSF en el documento **XEP-220: Server Dialback** <http://xmpp.org/extensions/xep-0220.html>define la negociación de Dialback. El proceso de Dialback del servidor usa el sistema de nombres de dominio (DNS) y un servidor autorizado para verificar que la solicitud procede de un socio XMPP válido. Para ello, el servidor de origen crea un mensaje de un tipo específico con una clave de Dialback generada y busca el servidor de recepción en DNS. El servidor de origen envía la clave en una secuencia XML a la búsqueda DNS resultante, supuestamente el servidor de recepción. Al recibir la clave sobre la secuencia XML, el servidor de recepción no responde al servidor de origen, pero envía la clave a un servidor conocido de autorización. El servidor autorizado verifica que la clave sea válida o no válida. Si no es válido, el servidor de recepción no responde al servidor de origen. Si la clave es válida, el servidor receptor informa al servidor de origen de que la identidad y la clave son válidas y que la conversación puede comenzar.
        
        Existen dos Estados válidos para la **negociación de Dialback**:
        
          - <span></span>  
            **Verdadero**. El servidor XMPP está configurado para usar la negociación de Dialback si se debe recibir una solicitud de un servidor de origen
        
          - <span></span>  
            **Falso**. El servidor XMPP no está configurado para usar la negociación de Dialback y si se debe recibir una solicitud de un servidor de origen, se pasará por alto.

</div>

</div>

<span> </span>

</div>

</div>

</div>

