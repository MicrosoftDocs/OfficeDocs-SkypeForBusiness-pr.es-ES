---
title: 'Lync Server 2013: Crear o editar la configuración de socios de XMPP'
TOCTitle: Crear o editar la configuración de socios de XMPP
ms:assetid: 362dbe5e-8ee9-4aba-8c26-5907312b4a60
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ552447(v=OCS.15)
ms:contentKeyID: 49115279
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Crear o editar la configuración de socios de XMPP en Lync Server 2013

 

_**Última modificación del tema:** 2016-12-08_

Microsoft Lync Server 2013 integra un proxy de protocolo extensible de mensajería y presencia (XMPP) en el Servidor perimetral y una puerta de enlace XMPP en el Servidor front-end o el Grupo de servidores front-end. Para permitir las conexiones procedentes de otras implementaciones de XMPP, debe configurar XMPP en el Panel de control de Lync Server. Las opciones de configuración se configuran por cada dominio XMPP. Para crear una nueva asociación de socio, lleve a cabo lo siguiente:

## Para crear un nuevo socio federado o editar una configuración existente

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y después introduzca la dirección URL de administración para abrir el panel de control de Lync Server. Para más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Abrir las herramientas administrativas de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Acceso externo y de federación** y, a continuación, haga clic en **Socios federados XMPP**.

4.  Para crear una nueva configuración, haga clic en **Nuevo**.

5.  Para editar una configuración existente, seleccione la configuración y haga clic en **Editar**

6.  Para crear o editar configuraciones de **Socios federados XMPP**, defina las opciones siguientes:

7.  **Dominio principal** (Obligatorio). El dominio principal es el dominio base del socio de XMPP. Por ejemplo, escriba **fabrikam.com** para el nombre de dominio de socio de XMPP. Es un campo obligatorio.

8.  **Descripción**. La descripción es para las notas u otra información de identificación de esta configuración determinada. Este campo es opcional.

9.  **Dominios adicionales**. Los dominios adicionales son los dominios que forman parte del dominio de su socio XMPP y que deben incluirse como parte de la comunicación XMPP permitida. Por ejemplo, si el dominio principal es **fabrikam.com**, debe incluir todos los demás dominios que se encuentren en fabrikam.com y con los que desee comunicarse mediante XMPP. Por ejemplo, puede especificar **corp.fabrikam.com** e **it.fabrikam.com** para el dominio XMPP corporativo y el dominio de tecnologías de información XMPP en el dominio XMPP principal de fabrikam.com.

10. **Tipo de socio**. El **Tipo de socio** es un valor obligatorio que ofrece una selección de tres opciones en un menú desplegable. Debe seleccionar una de las opciones siguientes para describir y aplicar el tipo de contacto que pueden agregarse. Puede seleccionar lo siguiente:
    
      - **Federado**. Un tipo de socio **Federado** representa una conexión de confianza entre un Lync Server o una implementación de socio de Office Communications Server 2007 R2.
    
      - **Público comprobado**. Los socios son del tipo **público comprobado** cuando los contactos que forman parte de una implementación comprobada por el proveedor pueden agregarse a su lista de contactos. Las invitaciones pueden enviarse desde el usuario de Lync o el usuario de Lync puede aceptar las invitaciones desde el contacto del socio.
    
      - **Público no comprobado**. Una relación **pública no comprobada** implica que no hay ningún estado establecido comprobable entre las dos implementaciones. Un usuario de Lync debe invitar al contacto no comprobado para poder agregar el usuario de Lync a su lista de contactos. Por ejemplo, Google GTalk no es un servicio XMPP público comprobado, ya que está relacionado con un Lync Server. Por lo tanto, un usuario de GTalk no podrá agregar al usuario de Lync como contacto a menos que el usuario de Lync haya enviado una invitación explícita.

11. Notas sobre la negociación de flujo y los métodos de seguridad Seguridad de la capa de transporte (TLS) y Autenticación de software y capa de seguridad (SASL):
    
    **XMPP Standards Foundation** (XSF) e **Internet Engineering Task Force** (IETF) definen un conjunto de reglas y estándares para el uso y la administración de certificados de clientes TLS, certificados de servidores TLS y del mecanismo SASL. La utilización de TLS y SASL es un proceso obligatorio para la protección del flujo XMPP. El documento de estándares XMPP **XEP-0178**, “especifica un flujo de protocolo recomendado para el uso del mecanismo SASL EXTERNO con certificados PKIX, sobre todo cuando un servicio XMPP indica que TLS es de negociación obligatoria.” PKIX, tal como indica la documentación de XSF, se refiere a la infraestructura de claves públicas, también conocida como PKI.
    
    Consulte el documento XEP-0178 de XSF para obtener más información sobre los requisitos de XMPP. Para obtener información detallada, consulte “XEP-0178: Procedimientos recomendados para el uso de SASL EXTERNO con certificados”. <http://xmpp.org/extensions/xep-0178.html>
    
    Consulte el documento de IETF “Protocolo extensible de mensajería y presencia (XMPP): Aspectos fundamentales“, la sección 5.0 sobre negociación STARTTLS <http://tools.ietf.org/html/rfc6120>.
    
      - **Negociación TLS**. Define las reglas de negociación de TLS. Un servicio de XMPP puede requerir TLS, determinar que TLS es opcional o definir que TLS no se admite. Si se opta por la posibilidad opcional, es el servicio de XMPP quien decide si la negociación es obligatoria. Para ver todos los valores posibles y detalles de negociación de rellamada, TLS y SASL, incluidas las configuraciones incorrectas conocidas y las no válidas, consulte [Configuración de la negociación para socios federados XMPP en Lync Server 2013](lync-server-2013-negotiation-settings-for-xmpp-federated-partners.md).
        
          -   
            **Obligatorio**. El servicio de XMPP requiere la negociación TLS.
        
          -   
            **Opcional**. El servicio de XMPP determina que TLS es de negociación obligatoria.
        
          -   
            **No admitido**. El servicio de XMPP no admite TLS.
    
      - **Negociación SASL**. Define las reglas de negociación de SASL. Un servicio de XMPP puede requerir SASL, determinar que SASL sea opcional o definir que SASL no se admite. Si se opta por la posibilidad opcional, es el servicio de XMPP de socio quien decide si la negociación es obligatoria.
        
        > [!WARNING]  
        > SASL requiere TLS. Para utilizar SASL, TLS debe ser obligatorio u opcional. Cualquier configuración que defina SASL como obligatorio u opcional debe ser compatible con TLS. Al hacer clic en <strong>Confirmar</strong> para guardar los cambios, si no ha establecido TLS como obligatorio u opcional, se mostrará una advertencia que indica que SASL debe ser compatible con TLS y que los cambios no se han guardado. Para resolver el error, establezca TLS como <strong>Obligatorio</strong> u <strong>Opcional</strong>. Si el uso de SASL es opcional y la negociación TLS no es posible, deberá establecer la negociación SASL como <strong>No compatible</strong>. Confirme con el servicio XMPP que los flujos de negociación adecuados deben ser para TLS y SASL o se producirá una interrupción en el servicio.
        
        
          -   
            **Obligatorio**. El servicio de XMPP requiere la negociación SASL.
        
          -   
            **Opcional**. El servicio de XMPP determina que SASL es de negociación obligatoria.
        
          -   
            **No admitido**. El servicio de XMPP no admite SASL.
    
      - **Negociación de devolución de llamada**. La negociación de devolución de llamada se define en XSF en el documento **XEP-220: Devolución de llamada del servidor**<http://xmpp.org/extensions/xep-0220.html>. El proceso de devolución de llamada del servidor usa el sistema de nombres de dominio (DNS) y un servidor relevante para comprobar que la solicitud procedía de un socio XMPP válido. Para ello, el servidor de origen crea un mensaje específico con una clave de devolución de llamada generada y busca el servidor de recepción en el DNS. El servidor de origen envía la clave en una secuencia XML a la búsqueda de DNS resultante, supuestamente al servidor de recepción. Al recibir la clave enviada a través de la secuencia XML, el servidor de recepción no responde al de origen pero envía una clave a un servidor relevante conocido. El servidor relevante comprueba si la clave es o no válida. Si no es válida, el servidor de recepción no responde al servidor de origen. Si la clave es válida, el servidor de recepción informa al servidor de origen que la identidad y la clave son válidas y se inicia la conversación.
        
        Existen dos estados válidos en la **negociación de rellamada**:
        
          -   
            **True**. El servidor XMPP está configurado para usar la negociación de devolución de llamada si se recibe una solicitud de un servidor de origen.
        
          -   
            **False**. El servidor XMPP no está configurado para usar la negociación de devolución de llamada y si se recibe una solicitud de un servidor de origen, esta se ignorará.

