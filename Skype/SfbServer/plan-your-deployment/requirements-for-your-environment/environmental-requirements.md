---
title: Requisitos del entorno para Skype Empresarial Server 2015
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 2/15/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 4812c444-2546-48d7-9ca7-b71fce508ed8
description: 'Resumen: Configurar sus requerimientos sin servidor de Skype para Business Server 2015. Hay una variedad de cosas que deseará configurado antes de realizar la implementación, incluyendo Active Directory, DNS, certificados y archivos compartidos.'
ms.openlocfilehash: 0d71140678654442caef112f6132695c76d3ea6c
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="environmental-requirements-for-skype-for-business-server-2015"></a>Requisitos del entorno para Skype Empresarial Server 2015
 
**Resumen:** Configurar sus requerimientos sin servidor de Skype para Business Server 2015. Hay una variedad de cosas que deseará configurado antes de realizar la implementación, incluyendo Active Directory, DNS, certificados y archivos compartidos.
  
¿Qué es un requisito ambiental de Skype para Business Server 2015? Bueno, hemos todo lo que no es directamente relacionado en este tema, por lo que no tienes que hacer como mucho clic alrededor de servidor. Si está buscando requisitos previos del servidor, puede desproteger el documento [requisitos del servidor para Skype para Business Server 2015](server-requirements.md) [Planificación de redes](../../plan-your-deployment/network-requirements/network-requirements.md) también se documenta por separado. De lo contrario, esto es lo que tenemos en este artículo:
  
- [Active Directory](environmental-requirements.md#AD)
  
- [Sistema de nombre de dominio (DNS)](environmental-requirements.md#DNS)
  
- [Certificados](environmental-requirements.md#Certs)
  
- [Recurso compartido de archivos](environmental-requirements.md#Fileshare)
  
## <a name="active-directory"></a>Active Directory
<a name="AD"> </a>

Mientras que una gran cantidad de datos de configuración para servidores y servicios se almacena en Skype para el almacén de Administración Central de Business Server 2015, hay algunas cosas siguen almacenados en Active Directory:
  
|**Objetos de Active Directory**|**Tipos de objeto**|
|:-----|:-----|
|Extensiones de esquema  <br/> |Extensiones de objetos de usuario  <br/> |
||Extensiones de Lync Server 2013 y Lync Server 2010 mantener la compatibilidad con las anteriores versiones compatibles.  <br/> |
|Datos  <br/> |URI de SIP del usuario y otros parámetros de usuario  <br/> |
||Objetos de contacto para las aplicaciones (como la aplicación de grupo de respuesta y la aplicación del operador de conferencia).  <br/> |
||Datos publicados para lograr compatibilidad con versiones anteriores  <br/> |
||Un servicio punto de control (SCP) para el almacén de Administración Central.  <br/> |
||Cuenta de autenticación Kerberos (un objeto de equipo opcional)  <br/> |
   
### <a name="os-for-domain-controllers"></a>SO para controladores de dominio

¿Qué SO de controladores de dominio se pueden usar? Tenemos la siguiente lista:
  
- Windows Server 2016
    
- Windows Server 2012 R2
    
- Windows Server 2012
    
- Windows Server 2008 R2
    
- Windows Server 2008
    
Ahora, el nivel funcional de dominio de cualquier dominio en que implementar Skype para Business Server 2015 y el nivel funcional del bosque de cualquier bosque implementar Skype para Business Server 2015, tienen que ser uno de los siguientes:
  
- Windows Server 2016
    
- Windows Server 2012 R2
    
- Windows Server 2012
    
- Windows Server 2008 R2
    
- Windows Server 2008
    
- Windows Server 2003
    
¿Puede haber controladores de dominio de solo lectura en estos entornos? Sí, mientras haya también disponible un controlador de dominio de escritura.
  
Ahora, es importante saber que Skype para el año 2015 de Business Server no es compatible con dominios de etiqueta única. ¿Qué son? Si tiene un dominio raíz de contoso.local, que va a estar bien. Si tiene un dominio raíz llamado simplemente local, que no va a trabajar y no se admite como resultado. Un poco más acerca de esto se ha escrito [en este artículo de Knowledge Base](https://support.microsoft.com/kb/300684/en-us).
  
Skype para Business Server 2015 también no admite el cambio de nombre de dominios. Si realmente tiene hacer, a continuación, que necesitará para desinstalar Skype para Business Server 2015, realice el cambio de nombre de dominio y, a continuación, vuelva a instalar Skype para Business Server 2015.
  
Por último, se puede estar tratando con un dominio con un entorno de AD DS bloqueado y tiene toda la razón. Contamos con más información sobre cómo implementar Skype para Business Server 2015 en ese tipo de entorno en los documentos de la implementación.
  
### <a name="ad-topologies"></a>Topologías de AD

Skype para topologías admitidas de 2015 Business Server son:
  
- Un solo bosque con un solo dominio
    
- Un solo bosque con un solo árbol y varios dominios
    
- Un solo bosque con varios árboles y espacios de nombres separados
    
- Varios bosques en una topología de bosque central
    
- Varios bosques en una topología de bosque de recursos
    
- Varios bosques en una topología de bosque de recursos de Skype Empresarial con Exchange Online
    
- Varios bosques en una topología de bosque de recursos con Skype Empresarial Online y Azure Active Directory Connect
    
Contamos con diagramas y descripciones para ayudarle a determinar qué topología tiene en su entorno, o lo que debe configurar antes de instalar Skype para Business Server 2015. Para no complicarlo, también incluimos una clave:
  
![Leyenda de los iconos usados en los diagramas de topología de Skype Empresarial](../../media/cc0dbc17-cf81-4b79-bf99-4614cc6828a0.png)
  
#### <a name="single-forest-with-single-domain"></a>Un solo bosque con un solo dominio

![Diagrama de un solo bosque de Active Directory con un único dominio](../../media/24921a0b-3a3e-4bad-8427-49300e2e3f7a.png)
  
No puede ser más fácil, es un bosque de dominio único, ésta es una topología común.
  
#### <a name="single-forest-with-a-single-tree-and-multiple-domains"></a>Un solo bosque con un solo árbol y varios dominios

![Diagrama de un solo bosque con un único árbol y varios dominios](../../media/63b9f0dd-6bac-4ba9-ae68-8be032d09dcb.png)
  
Este diagrama incluye también un único bosque, pero tiene también uno o más dominios secundarios (tres, en este ejemplo concreto). El dominio de en que los usuarios se crean podría ser diferente del dominio Skype para Business Server 2015 se implementa en. ¿Por qué esto es importante? Es importante recordar que cuando se implementa un Skype para el grupo de negocio de servidor Front-End, todos los servidores de ese grupo deben estar en un único dominio. Puede tener la administración de dominios a través de Skype para soporte del negocio servidor universal Administrador de grupos de Windows.
  
Al diagrama anterior, puede ver que los usuarios de un dominio tienen acceso a Skype para pools de Business Server del mismo dominio o en dominios diferentes, incluso si esos usuarios en un dominio secundario.
  
#### <a name="single-forest-with-multiple-trees-and-disjoint-namespaces"></a>Un solo bosque con varios árboles y espacios de nombres separados

![Diagrama de un solo bosque con varios árboles y espacios de nombres separados](../../media/5ede77a1-f5d2-499c-a2c8-d02f3c2f7cd7.png)
  
Puede ser que tiene una topología similar a este diagrama, donde haya un bosque, pero dentro de ese bosque son varios dominios, con espacios de nombres independientes de AD. Si ese es el caso, este diagrama de un buen ejemplo, como tenemos los usuarios en tres dominios diferentes acceso a Skype para Business Server 2015. Las líneas continuas indican que tiene acceso un Skype para el grupo de servidores de empresa en su propio dominio, mientras que una línea discontinua indica que van a un grupo en un árbol distinto por completo.
  
Como puede verse, todos los usuarios pueden acceder a los grupos, ya estén en el mismo dominio, en el mismo árbol o en un árbol diferente.
  
#### <a name="multiple-forests-in-a-central-forest-topology"></a>Varios bosques en una topología de bosque central

![Diagrama de varios bosques en una topología de bosque central](../../media/fec40746-4254-4c84-86b9-aad4a616ea2f.png)
  
Skype para el año 2015 de Business Server es compatible con varios bosques configurados en una topología de bosque central. Si no está seguro de que es lo que tiene, el bosque central en la topología utiliza objetos en ella para representar a los usuarios de los otros bosques y cuentas de usuario de hosts para todos los usuarios del bosque.
  
¿Cómo funciona? Bueno, un producto de sincronización de directorios (como Forefront Identity Manager o FIM) administra las cuentas de usuario de su organización a lo largo de su existencia. Cuando una cuenta se crea o elimina en un bosque, este cambio se sincroniza con el contacto correspondiente en el bosque central.
  
Claramente, si su infraestructura de AD es en lugar mover a esta topología puede no ser fácil, pero si ya está ahí o planificación todavía su infraestructura de bosque, esto puede ser una buena elección. Puede centralizar su Skype para implementación de Business Server 2015 dentro de un único bosque, mientras que los usuarios pueden buscar, comunicarse y ver la presencia de otros usuarios de cualquier bosque. Todas las actualizaciones de contactos del usuario se controlan automáticamente con el software de sincronización.
  
#### <a name="multiple-forests-in-a-skype-for-business-resource-forest-topology"></a>Varios bosques en una topología de bosque de recursos de Skype Empresarial
<a name="BKMK_multipleforestopology"> </a>

![Diagrama de varios bosques en una topología de bosque de recursos](../../media/41efa3b6-d9e6-47df-992b-fefcfc39a80d.png)
  
También se admite una topología de bosque de recursos; es donde un bosque está dedicado a la ejecución de las aplicaciones de servidor, como Microsoft Exchange Server y Skype para Business Server 2015. Bosques de este recurso también aloja una representación sincronizada de objetos de usuario activo, pero no cuentas de usuario de inicio de sesión. Por lo que el bosque de recursos es un entorno de servicios compartidos para otros bosques en la que residen los objetos de usuario y que tienen una relación de nivel de bosque de confianza con el bosque de recursos.
  
Tenga en cuenta que se puede implementar Exchange Server en el mismo bosque de recurso que Skype para Business Server o en un bosque diferente.
  
Para implementar Skype para Business Server 2015 en este tipo de topología, crearía un objeto de usuario deshabilitado en el bosque de recursos para cada cuenta de usuario en los bosques de usuario (si ya está en el entorno de Microsoft Exchange Server, esto puede hacerse para usted). A continuación, necesitará una herramienta de sincronización de directorios (como Forefront Identity Manager o FIM) administrar cuentas de usuario a través de su ciclo de vida.
  
#### <a name="multiple-forests-in-a-skype-for-business-resource-forest-topology-with-exchange-online"></a>Varios bosques en una topología de bosque de recursos de Skype Empresarial con Exchange Online
<a name="BKMK_multipleforestopology"> </a>

Esta topología es similar a la descrita en [Varios bosques en una topología de bosque de recursos de Skype Empresarial](environmental-requirements.md#BKMK_multipleforestopology).
  
En esta topología, hay uno o más bosques de usuario y Skype para Business Server se implementa en un bosque de recursos dedicado. Exchange Server puede ser implementado en instalaciones en el mismo bosque de recursos o en un bosque diferente y configurado para híbrido con Exchange Online o servicios de correo electrónico pueden proceder exclusivamente en línea de Exchange para las cuentas locales. No existe ningún diagrama disponible para esta topología.
  
#### <a name="multiple-forests-in-a-resource-forest-topology-with-skype-for-business-online-and-azure-active-directory-connect"></a>Varios bosques en una topología de bosque de recursos con Skype Empresarial Online y Azure Active Directory Connect
<a name="BKMK_multipleforestopology"> </a>

![Muestra dos bosques de AD, uno de usuario y uno de recurso. Ambos bosques tienen una relación de confianza y se sincronizan con Office 365 mediante Azure AD Connect. Todos los usuarios se habilitan para Skype Empresarial a través de Office 365.](../../media/6d54558d-8786-4ebf-90f6-55ae3fdb5ae7.jpg)
  
Con este escenario, hay varios bosques locales, con una topología de bosque de recursos. Hay una relación de total confianza entre los bosques de Active Directory. La herramienta Azure Active Directory Connect se utiliza para sincronizar cuentas entre los bosques de usuarios locales y Office 365.
  
 La organización también tiene Office 365 y utiliza el [Directorio activo de Azure Connect](https://go.microsoft.com/fwlink/p/?LinkId=614836) para sincronizar sus cuentas locales con Office 365. Los usuarios que están habilitados para Skype para empresas se activan mediante Office 365 y Skype para los negocios en línea. Skype para Business Server no está implementado en local.
  
Autenticación de inicio de sesión único proporciona un conjunto de servicios de federación de Active Directory ubicado en el bosque del usuario.
  
En este escenario, se admite para implementar Exchange locales, Exchange Online, una solución de Exchange híbrido, o no tiene Exchange implementado en absoluto. (El diagrama muestra solo Exchange local, pero las otras soluciones para Exchange también son totalmente compatibles).
  
#### <a name="multiple-forests-in-a-resource-forest-topology-with-hybrid-skype-for-business"></a>Varios bosques en una topología de bosque de recursos con una implementación híbrida de Skype Empresarial 
<a name="BKMK_multipleforestopology"> </a>

En este escenario, hay uno o más locales bosques de usuarios y Skype para empresas se implementa en un bosque de recursos dedicado y está configurado para modo híbrido con Skype para los negocios en línea. Exchange Server puede ser implementado en instalaciones en el mismo bosque de recursos o en un bosque diferente y puede configurarse para híbrido con Exchange Online. Como alternativa, servicios de correo electrónico pueden proceder exclusivamente en línea de Exchange para las cuentas locales.
  
Para obtener más información, consulte [configurar un entorno de varios bosque para híbrido Skype para el negocio](../../skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/configure-a-multi-forest-environment-for-hybrid.md).
  
## <a name="domain-name-system-dns"></a>Sistema de nombre de dominio (DNS)
<a name="DNS"> </a>

Skype para Business Server 2015 requiere DNS, por las siguientes razones:
  
- DNS permite Skype para Business Server 2015 descubrir servidores internos o agrupaciones, lo que permite comunicaciones de servidor a servidor.
    
- DNS permite al cliente equipos descubrir la piscina de Front-End o un servidor Standard Edition que se utiliza para transacciones SIP.
    
- Asocia las direcciones URL sencillas para conferencias con los servidores que hospedan dichas conferencias.
    
- DNS permite a los usuarios externos y los equipos cliente para conectarse a los servidores de borde, el proxy inverso HTTP, mensajería instantánea (IM) o conferencia.
    
- Comunicaciones unificadas (UC) permite detectar dispositivos que no se registran en la piscina de Front-End o un servidor Standard Edition que está ejecutando el servicio de actualización de dispositivo web para obtener actualizaciones y enviar registros.
    
- El uso de DNS permitir que los clientes móviles detecten automáticamente recursos de servicios web sin que los usuarios tengan que escribir manualmente las direcciones URL en la configuración del dispositivo.
    
- También se usa para el equilibrado de carga DNS.
    
Es importante destacar que Skype para Business Server 2015 no admite nombres de dominio internacionalizados (IDN).
  
Y es muy importante recordar que cualquier nombre en DNS sea idéntica al nombre del equipo configurado en cualquier servidor que esté usando Skype para Business Server 2015. Específicamente, nosotros no puede tener cualquier nombre de corto en el entorno y debe tener un FQDN para el generador de topología.
  
Esto parece que sería lógico para cualquier equipo que se ha unido a un dominio, pero si tienes un servidor perimetral que no está unido al dominio, puede tener un nombre corto, con el sufijo del dominio predeterminado. Asegúrese de que no es el caso, en DNS o en el servidor perimetral o cualquier Skype para Business Server 2015 o grupo de servidores, en realidad.
  
Y definitivamente no utilice caracteres Unicode o caracteres de subrayado. Los caracteres estándar (que son A-z, a-z, 0-9 y guiones) son los que van a ser compatibles DNS externo y entidades emisoras de certificados públicas (necesitará asignar el FQDN para el SN en el certificado, no se olvide), por lo que será repuesto usted mucha pena si nombre con esto en mente.
  
Si quiere más información sobre los requisitos de DNS para redes, consulte la sección [Networking](../../plan-your-deployment/network-requirements/network-requirements.md) de la documentación de planificación.
  
## <a name="certificates"></a>Certificados
<a name="Certs"> </a>

Unas de las cosas más importantes que puede hacer antes de la implementación es asegurarse de que sus certificados están en orden. Skype para Business Server 2015 necesita una infraestructura de claves públicas (PKI) de transporte capa de seguridad (TLS) y conexiones de seguridad (MTLS) de capa de transporte mutuo. Básicamente, para comunicarse de forma segura en una manera estandarizada, Skype para Business Server utiliza los certificados emitidos por entidades emisoras de certificados (CA).
  
Éstas son algunas de las cosas que Skype para Business Server 2015 utiliza certificados para:
  
- Conexiones TLS entre clientes y servidores
    
- Conexiones MTLS entre servidores
    
- Federación mediante la detección automática de DNS de socios
    
- Acceso de usuarios remotos a la mensajería instantánea (MI)
    
- Acceso de usuarios externos a sesiones de audio/vídeo (A/V), a uso compartido de aplicaciones y a conferencias
    
- Hablando con aplicaciones web y Outlook Web Access (OWA)
    
Planificación de certificado de SO indispensable. Ahora, echemos un vistazo a una lista de algunas de las cosas que debe tener en cuenta al solicitar certificados:
  
- Todos los certificados de servidor deben admitir la autorización de servidor (EKU de servidor).
    
- Todos los certificados de servidor deben contener un punto de distribución CRL (CDP).
    
- Todos los certificados deben estar firmados mediante un algoritmo de firma compatible con el sistema operativo. Skype para Business Server 2015 admite el SHA-1 y SHA-2 suite de síntesis tamaños (224, 256, 384 y 512 bits) y cumple o supera los requisitos del sistema operativo.
    
- La inscripción automática es compatible con los servidores internos con Skype para Business Server 2015.
    
- La inscripción automática no se admite para Skype para servidores de borde de Business Server 2015.
    
- Cuando envíe una solicitud de certificado basada en web a una CA de Windows Server 2003, debe enviar desde un equipo que ejecuta cualquier Windows Server 2003 con SP2 o Windows XP.
    
> [!NOTE]
> Aunque KB922706 ofrece soporte técnico para resolver problemas relacionados con los certificados web de inscripción de una inscripción web de los servicios de certificados de Windows Server 2003, no permite el uso de Windows Server 2008, Windows Vista o Windows 7 para solicitar un certificado desde una entidad de certificación de Windows Server 2003. 
  
> [!NOTE]
> No está permitido usar el algoritmo de firma RSASSA-PSS, ya que podría dar lugar a errores en problemas relacionados con el inicio de sesión y el desvío de llamadas, entre otros.  
  
- Se admiten longitudes de clave de cifrado de 1024, 2048 y 4096. Se recomienda usar longitudes de clave de 2048 y superiores.
    
- El algoritmo de firma hash o implícito predeterminado es RSA. También se admiten los algoritmos ECDH_P256, ECDH_P384 y ECDH_P521.
    
Eso es mucho para pensar y, definitivamente, hay una variedad de niveles de confort con solicitar certificados de una entidad emisora de certificados. Le daremos algunos consejos más detallados a continuación para hacer que la planeación sea lo más sencillo posible.
  
### <a name="certificates-for-your-internal-servers"></a>Certificados para los servidores internos

Necesitará certificados para la mayoría de los servidores internos, y es probable que se obtendrá de una entidad emisora de certificados interna (es decir, uno ubicado en el dominio). Si quiere, puede solicitar estos certificados a una CA externa (localizada en Internet). Si se está preguntando qué CA pública deben ir a, puede consultar la lista de [asociados de negocios de certificados de comunicaciones unificadas](https://support.microsoft.com/kb/929395/en-us) .
  
También va a necesitar certificados cuando Skype para Business Server 2015 se comunica con otras aplicaciones y servidores, como Microsoft Exchange Server. Obviamente, debe tratarse de certificados que estas otras aplicaciones y servidores admitan. Skype para Business Server 2015 y otros productos de Microsoft admite el protocolo de autorización abierta (OAuth) para la autorización y autenticación de servidor a servidor. Si está interesado en esto, tenemos un artículo de planificación adicional para OAuth y Skype para Business Server 2015.
  
Skype para el año 2015 de servidor empresarial también incluye compatibilidad para (sin necesidad) certificados firmados con la función de hash criptográfico SHA-256. Para permitir el acceso externo mediante SHA-256, una entidad de certificación pública que usa SHA-256 emite el certificado externo.
  
Para intentar mantener las cosas sencilla, hemos los requisitos de certificado para servidores Standard Edition, Front-End grupos y otras funciones en las tablas siguientes, con el que se utiliza para ejemplos (que probablemente utilizará algo de contoso.com ficticia Else para su entorno). Se trata de todos los certificados de servidor web estándar, con las claves privadas que están no exportable. Aspectos adicionales que tenga en cuenta:
  
- El uso mejorado de clave (EKU) del servidor se configura automáticamente al usar el asistente para certificados para solicitar certificados.
    
- El nombre descriptivo de cada certificado debe ser único en el almacén del equipo.
    
- Según los nombres de ejemplo siguiente, si ha configurado sipinternal.contoso.com o sipexternal.contoso.com en su DNS, deben agregarse a nombre de alternativa de asunto del certificado (SAN).
    
Certificados para servidores Standard Edition:
  
|**Certificado**|**Nombre común o nombre del sujeto**|**Nombre alternativo del sujeto**|**Ejemplo**|**Comentarios**|
|:-----|:-----|:-----|:-----|:-----|
|Predeterminado  <br/> |FQDN del grupo de servidores  <br/> |FQDN del grupo y FQDN del servidor  <br/> Si hay varios dominios SIP y está habilitada la configuración automática de los clientes, el Asistente para certificados detectará y agregará los FQDN de todos los dominios SIP admitidos.  <br/> Si este grupo de servidores es el servidor de inicio automático de sesión de los clientes y se requiere una correspondencia exacta del sistema de nombres de dominio (DNS) en la directiva del grupo, necesitará también entradas para sip.sipdomain (para cada uno de los dominios SIP que tenga).  <br/> |SN=se01.contoso.com; SAN=se01.contoso.com  <br/> Si este grupo de servidores es el servidor de inicio automático de sesión de los clientes y se requiere una correspondencia exacta de DNS en la directiva del grupo, necesitará también SAN=sip.contoso.com; SAN=sip.fabrikam.com  <br/> |En servidor de Standard Edition de servidores Standard Edition, el FQDN del servidor es el mismo que el FQDN del grupo.  <br/> El asistente detecta todos los dominios SIP especificados durante la instalación y los agrega automáticamente al nombre alternativo de sujeto.  <br/> También puede usar este certificado para la autenticación de servidor a servidor.  <br/> |
|Web interno  <br/> |FQDN del servidor  <br/> |Cada uno de los siguientes elementos:  <br/> • Interno web FQDN (que es el mismo que el FQDN del servidor)  <br/> Y  <br/> • Satisfacer simples direcciones de URL  <br/> • Acceso telefónico URL simple  <br/> • Administración sencilla URL  <br/> O BIEN  <br/> • Una entrada comodín para las direcciones URL simples  <br/> |SN=se01.contoso.com; SAN=se01.contoso.com; SAN=Meet.contoso.com; SAN=Meet.fabrikam.com; SAN=dialin.contoso.com; SAN=Admin.contoso.com  <br/> Con un certificado de comodín:  <br/> SN=se01.contoso.com; SAN=se01.contoso.com; SAN =\*. contoso.com  <br/> |No se puede reemplazar el web interno FQDN en el generador de topología.  <br/> Si dispone de varias URL sencillas de reunión, deberá incluirlas todas como nombres alternativos de sujeto.  <br/> Las entradas de comodín se admiten para las entradas de direcciones URL sencillas.  <br/> |
|Web externo  <br/> |FQDN del servidor  <br/> |Cada uno de los siguientes elementos:  <br/> • Externo web FQDN  <br/> Y  <br/> • Acceso telefónico URL simple  <br/> • Satisfacer simples direcciones URL por dominio SIP  <br/> O BIEN  <br/> • Una entrada comodín para las direcciones URL simples  <br/> |SN=se01.contoso.com; SAN=webcon01.contoso.com; SAN=Meet.contoso.com; SAN=Meet.fabrikam.com; SAN=dialin.contoso.com  <br/> Con un certificado de comodín:  <br/> SN=se01.contoso.com; SAN=webcon01.contoso.com; SAN =\*. contoso.com  <br/> |Si tiene varias direcciones URL simples satisfacer, tiene que incluir todos ellos como nombres alternativos del sujeto.  <br/> Las entradas de comodín se admiten para las entradas de direcciones URL sencillas.  <br/> |
   
Certificados para los servidores frontales en un grupo de servidores Front-End:
  
|**Certificado**|**Nombre común o nombre del sujeto**|**Nombre alternativo del sujeto**|**Ejemplo**|**Comentarios**|
|:-----|:-----|:-----|:-----|:-----|
|Predeterminado  <br/> |FQDN del grupo de servidores  <br/> |FQDN del grupo y FQDN del servidor  <br/> Si hay varios dominios SIP y está habilitada la configuración automática de los clientes, el Asistente para certificados detectará y agregará los FQDN de todos los dominios SIP admitidos.  <br/> Si este grupo de servidores es el servidor de inicio automático de sesión de los clientes y se requiere una correspondencia exacta del sistema de nombres de dominio (DNS) en la directiva del grupo, necesitará también entradas para sip.sipdomain (para cada uno de los dominios SIP que tenga).  <br/> |SN=eepool.contoso.com; SAN=eepool.contoso.com; SAN=ee01.contoso.com  <br/> Si este grupo de servidores es el servidor de inicio automático de sesión de los clientes y se requiere una correspondencia exacta de DNS en la directiva del grupo, necesitará también SAN=sip.contoso.com; SAN=sip.fabrikam.com  <br/> |El asistente detecta todos los dominios SIP especificados durante la instalación y los agrega automáticamente al nombre alternativo de sujeto.  <br/> También puede usar este certificado para la autenticación de servidor a servidor.  <br/> |
|Web interno  <br/> |FQDN del grupo de servidores  <br/> |Cada uno de los siguientes elementos:  <br/> • Interno web FQDN (que no es el mismo que el FQDN del servidor)  <br/> FQDN del servidor •  <br/> • Skype para el FQDN del grupo de negocio  <br/> Y  <br/> • Satisfacer simples direcciones de URL  <br/> • Acceso telefónico URL simple  <br/> • Administración sencilla URL  <br/> O BIEN  <br/> • Una entrada comodín para las direcciones URL simples  <br/> |SN=ee01.contoso.com; SAN=ee01.contoso.com; SAN=Meet.contoso.com; SAN=Meet.fabrikam.com; SAN=dialin.contoso.com; SAN=Admin.contoso.com  <br/> Con un certificado de comodín:  <br/> SN=ee01.contoso.com; SAN=ee01.contoso.com; SAN =\*. contoso.com  <br/> |Si tiene varias direcciones URL simples satisfacer, tiene que incluir todos ellos como nombres alternativos del sujeto.  <br/> Las entradas de comodín se admiten para las entradas de direcciones URL sencillas.  <br/> |
|Web externo  <br/> |FQDN del grupo de servidores  <br/> |Cada uno de los siguientes elementos:  <br/> • Externo web FQDN  <br/> Y  <br/> • Acceso telefónico URL simple  <br/> • Administración sencilla URL  <br/> O BIEN  <br/> • Una entrada comodín para las direcciones URL simples  <br/> |SN=ee01.contoso.com; SAN=webcon01.contoso.com; SAN=Meet.contoso.com; SAN=Meet.fabrikam.com; SAN=dialin.contoso.com  <br/> Con un certificado de comodín:  <br/> SN=ee01.contoso.com; SAN=webcon01.contoso.com; SAN =\*. contoso.com  <br/> |Si tiene varias direcciones URL simples satisfacer, tiene que incluir todos ellos como nombres alternativos del sujeto.  <br/> Las entradas de comodín se admiten para las entradas de direcciones URL sencillas.  <br/> |
   
Certificados para el Director:
  
|**Certificado**|**Nombre común o nombre del sujeto**|**Nombre alternativo del sujeto**|**Ejemplo**|
|:-----|:-----|:-----|:-----|
|Predeterminado  <br/> |Grupo de directores  <br/> |FQDN del Director, el FQDN del grupo de Director.  <br/> Si este grupo es el servidor de inicio de sesión automático para clientes y estricta DNS del necesaria la coincidencia en directiva de grupo, también necesitará entradas para sip.sipdomain (para cada dominio SIP que tiene).  <br/> |pool.contoso.com; SAN=dir01.contoso.com  <br/> Si este grupo de directores es el servidor de inicio de sesión automático para los clientes y es necesaria la coincidencia de DNS de strict en la directiva de grupo, deberá SAN=sip.contoso.com; SAN=SIP.fabrikam.com  <br/> |
|Web interno  <br/> |FQDN del servidor  <br/> |Cada uno de los siguientes elementos:  <br/> • Interno web FQDN (que es el mismo que el FQDN del servidor)  <br/> FQDN del servidor •  <br/> • Skype para el FQDN del grupo de negocio  <br/> Y  <br/> • Satisfacer simples direcciones de URL  <br/> • Acceso telefónico URL simple  <br/> • Administración sencilla URL  <br/> O BIEN  <br/> • Una entrada comodín para las direcciones URL simples  <br/> |SN=dir01.contoso.com; SAN=dir01.contoso.com; SAN=Meet.contoso.com; SAN=Meet.fabrikam.com; SAN=dialin.contoso.com; SAN=Admin.contoso.com  <br/> Con un certificado de comodín:  <br/> SN=dir01.contoso.com; SAN=dir01.contoso.com SAN =\*. contoso.com  <br/> |
|Web externo  <br/> |FQDN del servidor  <br/> |Cada uno de los siguientes elementos:  <br/> • Externo web FQDN  <br/> Y  <br/> • Satisfacer simples direcciones URL por dominio SIP  <br/> • Acceso telefónico URL simple  <br/> O BIEN  <br/> • Una entrada comodín para las direcciones URL simples  <br/> |El FQDN de web externo Director debe ser distinto del grupo de servidores Front-End o un servidor Front-End.  <br/> SN=dir01.contoso.com; SAN=meet.contoso.com de SAN=directorwebcon01.contoso.com; SAN=Meet.fabrikam.com; SAN=dialin.contoso.com  <br/> Con un certificado de comodín:  <br/> SN=dir01.contoso.com; SAN=directorwebcon01.contoso.com SAN =\*. contoso.com  <br/> |
   
Certificados de servidor de mediación independiente:
  
|**Certificado**|**Nombre común o nombre del sujeto**|**Nombre alternativo del sujeto**|**Ejemplo**|
|:-----|:-----|:-----|:-----|
|Predeterminado  <br/> |FQDN del grupo de servidores  <br/> |FQDN del grupo de servidores  <br/> FQDN del miembro del grupo de servidores  <br/> |SN = medsvr-pool.contoso.net; SAN = medsvr-pool.contoso.net; SAN=medsvr01.contoso .net  <br/> |
   
Certificados para el dispositivo de la rama que sobreviven:
  
|**Certificado**|**Nombre común o nombre del sujeto**|**Nombre alternativo del sujeto**|**Ejemplo**|
|:-----|:-----|:-----|:-----|
|Predeterminado  <br/> |FQDN de la aplicación  <br/> |SIP. \<sipdomain\> (necesita sólo una entrada por cada dominio SIP)  <br/> |SN=sba01.contoso. NET; SAN=SIP.contoso.com; SAN=SIP.fabrikam.com  <br/> |
   
### <a name="certificates-for-your-persistent-chat-server"></a>Certificados para el servidor de chat persistente

Al instalar al servidor de charla persistente, va a necesita un certificado emitido por la misma CA que el utilizado por su Skype para servidores internos Business Server 2015. Esto debe realizarse para cada servidor que ejecuta el persistente servicios Web de Chat para carga y descarga de archivos. Se recomienda tener el o los certificados necesarios antes de iniciar la instalación de charla persistente y si la entidad emisora de certificados es externo, más aún (estas cosas pueden tardar algo de tiempo para emitir).
  
### <a name="certificates-for-external-user-access-edge"></a>Certificados para el acceso de usuarios externos (Edge)

Skype para el año 2015 de Business Server admite el uso de un **único certificado público** de web y acceso a interfaces externas de borde de conferencias, además de la / servicio de autenticación de V, que se proporciona a través de los servidores de borde. La interfaz interna del borde normalmente utiliza un certificado privado emitido por la entidad emisora de certificados interna, pero si lo prefiere, puede utilizar un certificado público para esto, si proviene de una CA de confianza.
  
Su proxy inverso (RP) también usa un certificado público y cifra sus propias comunicaciones con los clientes y los servidores internos mediante HTTP (o, para ser más precisos, TLS por HTTP).
  
### <a name="certificates-for-mobility"></a>Certificados para movilidad

Si está implementando movilidad y está fomentando el descubrimiento automático para clientes móviles, va a necesitar incluir algunas entradas de nombre alternativo de sujeto adicional en sus certificados para admitir las conexiones seguras de los clientes móviles.
  
Estos son los certificados en los que necesitará nombres alternativos de sujeto para la detección automática:
  
- Grupo de directores
    
- Grupo de servidores front-end
    
- Proxy inverso
    
En las siguientes tablas se ofrecen detalles.
  
Ahora, esto es donde un poco de planificación previa es buena, pero a veces ha implementado Skype para Business Server 2015 sin intención de implementar la movilidad y que aparece abajo de la línea cuando ya tiene certificados en su entorno. Volver a emitir los certificados desde una CA interna suele ser sencillo, pero en el caso de una CA pública puede resultar un poco más caro.
  
Si eso es lo que estás buscando y tienes un montón de dominios SIP (que sería agregar SANS más costoso), puede configurar el proxy inverso para utilizar HTTP en la solicitud inicial de Autodiscover Service, en lugar de utilizar HTTPS (que es el predeterminado configuración). Tiene más información en el tema Planificación para la movilidad.
  
Requisitos de los certificados de grupo de director y Front-End:
  
|**Descripción**|**Entrada de SAN**|
|:-----|:-----|
|URL del servicio Detección automática interna  <br/> |SAN = lyncdiscoverinternal. \<sipdomain\>  <br/> |
|URL del servicio Detección automática externa  <br/> |SAN = lyncdiscover. \<sipdomain\>  <br/> |
   
También puede utilizar SAN =\*. \<sipdomain\>
  
Requisitos de certificado (CA pública) de proxy inverso
  
|**Descripción**|**Entrada de SAN**|
|:-----|:-----|
|URL del servicio Detección automática externa  <br/> |SAN = lyncdiscover. \<sipdomain\>  <br/> |
   
Este SAN debe asignarse al certificado asignado al agente de escucha SSL de su proxy inverso.
  
> [!NOTE]
> Curso el proxy inverso del agente de escucha que SANs para la URL de servicios Web externos. Algunos ejemplos serían SAN=skypewebextpool01.contoso.com y dirwebexternal.contoso.com, si ha implementado el Director, (que es opcional). 
  
## <a name="file-share"></a>Recurso compartido de archivos
<a name="Fileshare"> </a>

Skype para Business Server 2015 es capaz de utilizar el mismo recurso compartido de archivo para el almacenamiento de todos los archivos. Deberá tener en cuenta lo siguiente:
  
- Un recurso compartido de archivos debe estar en un almacenamiento conectado directo (DAS) o en un almacenamiento en red (SAN), y esto incluye el sistema de archivos distribuidos (DFS) y las matrices redundantes de discos independientes (RAID). Para obtener más información sobre DFS para Windows Server 2012, consulte [esta página DFS](https://technet.microsoft.com/en-us/library/jj127250.aspx).
    
- Se recomienda un clúster compartido para el recurso compartido de archivo. Si está utilizando uno, debe organizar en clústeres Windows Server 2012 o Windows Server R2 de 2012. Windows Server 2008 R2 también es aceptable. ¿Por qué el más reciente para Windows? Las versiones más antiguas no tenga los permisos adecuados para habilitar todas las características. Puede utilizar el Administrador de clústeres para crear los recursos compartidos de archivo y, en este artículo la [creación de un clúster](https://support.microsoft.com/kb/284838) KB le ayudará con esos detalles.
    
> [!CAUTION]
> Es preciso que recuerde que no se admite el uso del almacenamiento conectado a la red (NAS) como recurso compartido de archivo, de modo que utilice una de las opciones que se han descrito anteriormente. 
  

