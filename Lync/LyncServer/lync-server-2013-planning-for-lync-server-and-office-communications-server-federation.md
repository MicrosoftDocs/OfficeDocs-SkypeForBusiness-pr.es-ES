---
title: "Planif. pour la fédération de Lync Server et Office Communications Server"
TOCTitle: "Planif. pour la fédération de Lync Server et Office Communications Server"
ms:assetid: c9eaf06b-054f-41a4-ad0c-499400d6c4c7
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ205335(v=OCS.15)
ms:contentKeyID: 48276674
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Planeación de federación de Lync Server y Office Communications Server

 

_**Última modificación del tema:** 2013-02-13_

La federación entre Microsoft Lync Server 2013, Lync Server 2010 y Office Communications Server admite las comunicaciones de punto a punto y entre varias personas. Las conversaciones de punto a punto se pueden escalar a conversaciones entre varias personas, lo que permite las reuniones ad hoc. Las reuniones, las conferencias web o las conferencias de audio y vídeo se pueden programar para que incluyan contactos dentro de la organización, así como contactos en socios con los que haya establecido una relación de federación.

La federación apareció por primera vez en Microsoft Office Live Communications Server 2005 y admitía un tipo de federación, la federación directa. Se precisaba conocer el dominio del protocolo de inicio de sesión (SIP) del socio de la federación y el nombre de dominio completo (FDQN) de Servidor perimetral del socio. Live Communications Server 2005 con SP1 introdujo otros tipos de federación, que requerían que el socio federado publicase los registros SRV del sistema de nombres de dominio (DNS) para localizar Servidor perimetral. La terminología de aquella versión era:

  - *Federación mejorada abierta*: acepte cualquier nombre de dominio SIP y use SRV DNS para localizar Servidor perimetral del socio.

  - *Federación mejorada*: configure el nombre de dominio SIP del socio como socio de federación de la organización y use el SRV DNS apara localizar Servidor perimetral del socio.

  - *Federación directa*: configure el nombre de dominio SIP del socio y el FQDN para Servidor perimetral del socio.

  - *Lista de permisos del servidor*: acepte cualquier dominio, use el SRV DNS para localizar Servidor perimetral de un proveedor de hospedaje o un proveedor de conectividad de mensajería instantánea (MI).

Microsoft Office Communications Server 2007 introdujo una denominación nueva de los tipos de federación para definir mejor lo que se conseguía con cada tipo de federación:

  - La federación mejorada abierta se denominó *dominio de socio detectado*.

  - La federación mejorada se denominó *dominio de socio permitido*.

  - La federación directa se denominó *servidor de socio permitido*.

  - La lista de permisos del servidor se denominó *proveedor de hospedaje* y *proveedor de MI público*.

Microsoft Lync Server 2010 introdujo una definición más específica del proveedor de hospedaje de acuerdo con Microsoft Lync Online 2010 y Microsoft Office 365, y la sometió a la misma lista permitida que definía el tipo de federación de dominio de socio permitido.

La habilitación de la federación entre Microsoft Lync Server 2013, Lync Server 2010 y Office Communications Server usa los servidores proxy inversos de Servidores perimetrales para aplicar las reglas y los dominios de socios permitidos que defina. Desde una perspectiva de planeación, la federación con otros Lync Server, Office Communications Server requiere lo siguiente:

  - Habilite la federación en el Generador de topologías. Para más información, consulte el tema de la implementación [Configurar la federación SIP, la federación XMPP y la mensajería instantánea pública en Lync Server 2013](lync-server-2013-configuring-sip-federation-xmpp-federation-and-public-instant-messaging.md).

  - Determine sus requisitos para la detección de dominios federados:
    
      -   
        Para la configuración manual de la federación, debe tener un nombre de dominio completo (FQDN) de Servidor perimetral y un nombre de dominio, o un nombre de dominio en línea del socio, que se escribe en Panel de control de Lync Server, **Federación y acceso externo**, **Dominios federados SIP**. Cree una**nueva** directiva o **edite** una directiva actual para permitir o bloquear dominios por FQDN.
        
        > [!WARNING]  
        > La configuración manual de Servidor perimetral del socio de federación puede generar errores en caso de que el socio cambie la dirección IP de su Servidor perimetral.
        
        

        > [!NOTE]
        > Para los <STRONG>nuevos dominios federados SIP</STRONG>, debe proporcionar el <STRONG>nombre de dominio (o FQDN)</STRONG> para Microsoft Lync Online, Microsoft Office 365. Para Microsoft Lync Server 2013, Lync Server 2010 y Office Communications Server también debe proporcionar un <STRONG>servicio de servidor perimetral de acceso (FQDN)</STRONG>.

    
      -   
        Para una federación de socios abierta, en la que los socios detectan Servidor perimetral, puede crear un registro SRV en su DNS externo, \_sipfederationtls.\_tcp.contoso.com, que apunte al puerto 5061, y el registro de host (A) de Servidor perimetral.
        
        > [!IMPORTANT]  
        > Si admite clientes Microsoft Lync Mobile en Windows Phone o Apple iPhone, iPad u otros dispositivos Apple, y usan Servicios de notificaciones de inserción o Servicios de notificaciones de inserción, debe planear registros SRV _sipfederationtls._tcp. <em>&lt;dominio SIP&gt;</em> para cada dominio SIP donde tenga clientes Lync Mobile. Android y Nokia Symbian Lync Mobile no usan la notificación de inserción y no dependen de este requisito.
        


  - Configure las directivas de acceso de los usuarios externos para admitir los dominios federados.

  - Abra los puertos del firewall para el protocolo de inicio de sesión (SIP), las conferencias web y los audios y vídeos, con el fin de adaptar la federación o los contactos que está habilitando. Para más información, consulte: [Determinar los requisitos de los puertos y el firewall de A/V externos en Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md).

La información siguiente le ayudará en la definición del certificado, el puerto o el protocolo, y los requisitos DNS para la federación con Microsoft Lync Server 2013 y Lync Server 2010.

La planificación de certificados, requisitos de firewall, y de puerto y protocolo, y los requisitos DNS constituye generalmente un proceso muy sencillo si ha planificado o implementado Servidores perimetrales deMicrosoft Lync Server 2013. Como la federación es una característica adicional que usa Servidor perimetral actual, los requisitos de planificación se cumplen generalmente por parte de la planificación y la implementación de Servidor perimetral. Use las tablas siguientes para determinar si se cumplen los requisitos, y realizar los cambios en el puerto o el protocolo y en el DNS según convenga.

> [!IMPORTANT]  
> Si tiene un grupo de Servidores perimetrales y establece relaciones de federación con los socios de Lync Server 2013 o Lync Server 2010, puede usar el equilibrio de carga de DNS y los equilibradores de carga de hardware en las partes internas y externas de Servidores perimetrales. Si establece relaciones de federación con Office Communications Server 2007 o Office Communications Server 2007 R2, el equilibrio de carga de hardware ofrecerá asistencia de conmutación por error en el caso de un Servidor perimetral. El equilibrio de carga de DNS de Office Communications Server 2007 y Office Communications Server 2007 R2 no es consciente del equilibrio de carga de DNS. El socio Servidores perimetrales establecerá comunicación con el primer Servidor perimetral de su grupo. Si este Servidor perimetral genera errores, la comunicación no se conmutará automáticamente por error.



Los requisitos de certificado normalmente se cumplen a través de la planeación de certificados del plan de Servidor perimetral elegido, o de Servidor perimetral agrupado.

## En esta sección

  - [Resumen de certificados: federación SIP, federación XMPP y mensajería instantánea pública](lync-server-2013-certificate-summary-sip-xmpp-federation-and-public-instant-messaging.md)

  - [Resumen de puerto: federación SIP, federación XMPP y mensajería instantánea pública](lync-server-2013-port-summary-sip-xmpp-federation-and-public-instant-messaging.md)

  - [Resumen de DNS: federación SIP, federación XMPP y mensajería instantánea pública](lync-server-2013-dns-summary-sip-xmpp-federation-and-public-instant-messaging.md)

## Vea también

#### Tareas

[Configurar directivas para controlar el acceso de usuarios federados en Lync Server 2013](lync-server-2013-configure-policies-to-control-federated-user-access.md)  

#### Conceptos

[Escenarios para el acceso de usuarios externos en Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md)  
[Determinar los requisitos de los puertos y el firewall de A/V externos en Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)  
[Determinar los requisitos DNS para Lync Server 2013](lync-server-2013-determine-dns-requirements.md)  

#### Otros recursos

[Administrar la configuración perimetral de acceso para su organización en Lync Server 2013](lync-server-2013-manage-access-edge-configuration-for-your-organization.md)  
[Administrar dominios federados SIP para la organización en Lync Server 2013](lync-server-2013-manage-sip-federated-domains-for-your-organization.md)  
[Administrar proveedores federados SIP para la organización en Lync Server 2013](lync-server-2013-manage-sip-federated-providers-for-your-organization.md)

