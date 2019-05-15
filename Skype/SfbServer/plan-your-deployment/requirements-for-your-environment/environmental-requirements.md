---
title: Requisitos del entorno para Skype Empresarial Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/15/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 4812c444-2546-48d7-9ca7-b71fce508ed8
description: 'Resumen: Configurar los requisitos de servidor que no sean de Skype para Business Server 2015. Hay una gran variedad de cosas que querrá configurado antes de realizar la implementación, incluidos Active Directory, DNS, certificados y uso compartido de archivos.'
ms.openlocfilehash: 71916081a9ea138d22f41fd4f2813834a74e941b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33909081"
---
# <a name="environmental-requirements-for-skype-for-business-server-2015"></a>Environmental requirements for Skype for Business Server 2015
 
**Resumen:** Configurar los requisitos de servidor que no sean de Skype para Business Server 2015. Hay una gran variedad de cosas que querrá configurado antes de realizar la implementación, incluidos Active Directory, DNS, certificados y uso compartido de archivos.
  
¿Qué es un requisito del entorno de Skype para Business Server 2015? Bueno, hemos todo lo que no es directamente relacionado en este tema, por lo que no tiene que hacer como mucho al hacer clic en alrededor de servidor. Si está buscando requisitos previos del servidor, puede desproteger el doc. [requisitos de servidor para Skype para Business Server 2015](server-requirements.md) [Planeación de la red](../../plan-your-deployment/network-requirements/network-requirements.md) está documentado también por separado. De lo contrario, esto es lo que tenemos en este artículo:
  
- [Active Directory](environmental-requirements.md#AD)
  
- [Sistema de nombre de dominio (DNS)](environmental-requirements.md#DNS)
  
- [Certificados](environmental-requirements.md#Certs)
  
- [Recurso compartido de archivos](environmental-requirements.md#Fileshare)
  
## <a name="active-directory"></a>Active Directory
<a name="AD"> </a>

Mientras que una gran cantidad de datos de configuración de los servidores y servicios se almacena en Skype para el almacén de Administración Central del negocio Server 2015, hay algunas cosas que siguen almacenados en Active Directory:
  
|**Objetos de Active Directory**|**Tipos de objeto**|
|:-----|:-----|
|Extensiones de esquema  <br/> |Extensiones de objetos de usuario  <br/> |
||Versiones compatibles de extensiones para Lync Server 2013 y Lync Server 2010 mantener la compatibilidad con versiones anteriores con el anterior.  <br/> |
|Datos  <br/> |URI de SIP del usuario y otros parámetros de usuario  <br/> |
||Objetos de contacto para aplicaciones (como la aplicación de grupo de respuesta y la aplicación operador de conferencia).  <br/> |
||Datos publicados para lograr compatibilidad con versiones anteriores  <br/> |
||Un servicio punto de control (SCP) para el almacén de Administración Central.  <br/> |
||Cuenta de autenticación Kerberos (un objeto de equipo opcional)  <br/> |
   
### <a name="os-for-domain-controllers"></a>SO para controladores de dominio

¿Qué SO de controladores de dominio se pueden usar? Tenemos la siguiente lista:
  
- Windows Server 2016
    
- Windows Server 2012 R2
    
- Windows Server 2012
    
- Windows Server 2008 R2
    
- Windows Server 2008
    
Ahora, el nivel funcional de dominio de cualquier dominio en que implementar Skype para Business Server 2015 y el nivel funcional de bosque de cualquier bosque implementar Skype para Business Server 2015 en, tienen que ser una de las siguientes opciones:
  
- Windows Server 2016
    
- Windows Server 2012 R2
    
- Windows Server 2012
    
- Windows Server 2008 R2
    
- Windows Server 2008
    
- Windows Server 2003
    
¿Puede haber controladores de dominio de solo lectura en estos entornos? Sí, mientras haya también disponible un controlador de dominio de escritura.
  
Ahora, es importante saber que Skype para Business Server 2015 no admite dominios de etiqueta única. ¿Qué son? Si tiene un dominio raíz con la etiqueta contoso.local, que se va a estar bien. Si tiene un dominio raíz sólo con el nombre local, que no se va a trabajar y no se admite como resultado. Un poco más acerca de esto se ha escrito [en este artículo de Knowledge Base](https://support.microsoft.com/kb/300684/en-us).
  
Skype para Business Server 2015 también no admite el cambio de nombre de dominios. Si realmente tiene hacer, a continuación, se aquí necesita desinstalar Skype para Business Server 2015, realice el cambio de nombre de dominio y, a continuación, vuelva a instalar Skype para Business Server 2015.
  
Por último, se puede estar tratando con un dominio con un entorno de AD DS bloqueados, y que son todos los derechos. Hemos desarrollado para obtener más información acerca de cómo implementar Skype para Business Server 2015 en ese tipo de entorno en los documentos de implementación.
  
### <a name="ad-topologies"></a>Topologías de AD

Skype para topologías admitidas de 2015 Business Server son:
  
- Un solo bosque con un solo dominio
    
- Un solo bosque con un solo árbol y varios dominios
    
- Un solo bosque con varios árboles y espacios de nombres separados
    
- Varios bosques en una topología de bosque central
    
- Varios bosques en una topología de bosque de recursos
    
- Varios bosques en una topología de bosque de recursos de Skype Empresarial con Exchange Online
    
- Varios bosques en una topología de bosque de recursos con Skype Empresarial Online y Azure Active Directory Connect
    
Disponemos de diagramas y descripciones que le ayudarán a determinar qué topología tiene en su entorno, o lo que es posible que necesite configurar antes de instalar Skype para Business Server 2015. Para mantener la simple, también incluimos una clave:
  
![Leyenda de los iconos usados en los diagramas de topología de Skype Empresarial](../../media/cc0dbc17-cf81-4b79-bf99-4614cc6828a0.png)
  
#### <a name="single-forest-with-single-domain"></a>Un solo bosque con un solo dominio

![Diagrama de un solo bosque de Active Directory con un único dominio](../../media/24921a0b-3a3e-4bad-8427-49300e2e3f7a.png)
  
No puede ser más fácil que esto, es un bosque de dominio único, se trata de una topología común.
  
#### <a name="single-forest-with-a-single-tree-and-multiple-domains"></a>Un solo bosque con un solo árbol y varios dominios

![Diagrama de un solo bosque con un único árbol y varios dominios](../../media/63b9f0dd-6bac-4ba9-ae68-8be032d09dcb.png)
  
Este diagrama incluye también un único bosque, pero tiene también uno o más dominios secundarios (tres, en este ejemplo concreto). Por lo que el dominio de en que los usuarios se crean puede ser diferente del dominio Skype para Business Server 2015 se implementa en. ¿Por qué esto es importante? Es importante recordar que cuando se implementa un Skype para grupo de negocio de servidor Front-End, todos los servidores de ese grupo de servidores deben estar en un solo dominio. Puede tener la administración entre dominios a través de Skype para soporte técnico del servidor empresarial de grupos de administradores universales de Windows.
  
Copia en el diagrama anterior, puede ver que los usuarios de un dominio tienen acceso a Skype para grupos de servidores de negocio desde el mismo dominio o de dominios diferentes, incluso si los usuarios se encuentran en un dominio secundario.
  
#### <a name="single-forest-with-multiple-trees-and-disjoint-namespaces"></a>Un solo bosque con varios árboles y espacios de nombres separados

![Diagrama de un solo bosque con varios árboles y espacios de nombres separados](../../media/5ede77a1-f5d2-499c-a2c8-d02f3c2f7cd7.png)
  
Es posible que tiene una topología similar a este diagrama, donde tiene uno de los bosques, pero dentro de ese bosque son varios dominios, con espacios de nombres independientes de AD. Si ese es el caso, este diagrama s una ilustración buena, tal y como hemos desarrollado a los usuarios en diferentes tres dominios acceso a Skype para Business Server 2015. Las líneas continuas indican que tiene acceso un Skype para grupo de servidores de negocio en su propio dominio, mientras que una línea discontinua indica que va a un grupo de servidores en un árbol diferente por completo.
  
Como puede verse, todos los usuarios pueden acceder a los grupos, ya estén en el mismo dominio, en el mismo árbol o en un árbol diferente.
  
#### <a name="multiple-forests-in-a-central-forest-topology"></a>Varios bosques en una topología de bosque central

![Diagrama de varios bosques en una topología de bosque central](../../media/fec40746-4254-4c84-86b9-aad4a616ea2f.png)
  
Skype para Business Server 2015 es compatible con varios bosques configurados en una topología de bosque central. Si no está seguro de que es lo que tiene, el bosque central en la topología utiliza objetos en ella para representar a los usuarios en los otros bosques y las cuentas de usuario de hosts de los usuarios en el bosque.
  
¿Cómo funciona? Bueno, un producto de sincronización de directorios (por ejemplo, Forefront Identity Manager, o FIM) administra las cuentas de usuario de su organización a lo largo de su existencia. Cuando una cuenta se crea o elimina en un bosque, este cambio se sincroniza con el contacto correspondiente en el bosque central.
  
Sin lugar a dudas, si la infraestructura de AD es inmediata mover a esta topología es posible que no sea fácil, pero si ya está allí, o aún planeación su infraestructura de bosque, esto puede ser una buena opción. Puede centralizar su Skype para la implementación empresarial Server 2015 dentro de un solo bosque, mientras que los usuarios pueden buscar, comunicarse y ver la presencia de otros usuarios en cualquier bosque. Todas las actualizaciones de contacto de usuario se controlan automáticamente con el software de sincronización.
  
#### <a name="multiple-forests-in-a-skype-for-business-resource-forest-topology"></a>Varios bosques en una topología de bosque de recursos de Skype Empresarial
<a name="BKMK_multipleforestopology"> </a>

![Diagrama de varios bosques en una topología de bosque de recursos](../../media/41efa3b6-d9e6-47df-992b-fefcfc39a80d.png)
  
También se admite una topología de bosque de recursos; es donde un bosque está dedicado a la ejecución de las aplicaciones de servidor, como Microsoft Exchange Server y Skype para Business Server 2015. Este bosques de recursos también hospeda una representación sincronizada de objetos de usuario activo, pero no las cuentas de usuario habilitado para el inicio de sesión. Por lo que el bosque de recursos es un entorno de servicios compartidos para otros bosques en la que residen objetos de usuario y tienen una relación de confianza de nivel de bosque con el bosque de recursos.
  
Tenga en cuenta que se puede implementar Exchange Server en el mismo bosque de recursos como Skype para Business Server o en un bosque diferente.
  
Para implementar Skype para Business Server 2015 en este tipo de topología, crearía un objeto de usuario deshabilitado en el bosque de recursos para cada cuenta de usuario en los bosques de usuarios (si ya está en el entorno de Microsoft Exchange Server, esto puede hacerse para usted). A continuación, necesitará una herramienta de sincronización de Active directory (como Forefront Identity Manager, o FIM) para administrar cuentas de usuario a través de su ciclo de vida.
  
#### <a name="multiple-forests-in-a-skype-for-business-resource-forest-topology-with-exchange-online"></a>Varios bosques en una topología de bosque de recursos de Skype Empresarial con Exchange Online
<a name="BKMK_multipleforestopology"> </a>

Esta topología es similar a la descrita en [Varios bosques en una topología de bosque de recursos de Skype Empresarial](environmental-requirements.md#BKMK_multipleforestopology).
  
En esta topología, hay uno o más bosques de usuarios y Skype para Business Server se implementa en un bosque de recursos dedicado. Exchange Server puede ser instalados en servidores locales en el mismo bosque de recursos o de un bosque diferente y configurado para la implementación híbrida con Exchange Online, o se pueden proporcionar servicios de correo electrónico exclusivamente por Exchange Online para las cuentas locales. No existe ningún diagrama disponible para esta topología.
  
#### <a name="multiple-forests-in-a-resource-forest-topology-with-skype-for-business-online-and-azure-active-directory-connect"></a>Varios bosques en una topología de bosque de recursos con Skype Empresarial Online y Azure Active Directory Connect
<a name="BKMK_multipleforestopology"> </a>

![Muestra dos bosques de AD, uno de usuario y uno de recurso. Ambos bosques tienen una relación de confianza y se sincronizan con Office 365 mediante Azure AD Connect. Todos los usuarios se habilitan para Skype Empresarial a través de Office 365.](../../media/6d54558d-8786-4ebf-90f6-55ae3fdb5ae7.jpg)
  
Con este escenario, hay varios bosques locales, con una topología de bosque de recursos. Hay una relación de total confianza entre los bosques de Active Directory. La herramienta Azure Active Directory Connect se utiliza para sincronizar cuentas entre los bosques de usuarios locales y Office 365.
  
 La organización también tiene Office 365 y [Azure Active Directory Connect](https://go.microsoft.com/fwlink/p/?LinkId=614836) utiliza para sincronizar sus cuentas locales con Office 365. Los usuarios habilitados para Skype para la empresa están habilitados a través de Office 365 y Skype para profesionales en línea. Skype para Business Server no está instalados en servidores locales.
  
Autenticación de inicio de sesión único es proporcionada por una granja de servidores de servicios de federación de Active Directory que se encuentra en el bosque de usuarios.
  
En este escenario, se admite para implementar Exchange local, Exchange Online, una solución híbrida de Exchange, o bien de no tener Exchange implementado en absoluto. (El diagrama muestra solo Exchange local, pero las otras soluciones para Exchange también son totalmente compatibles).
  
#### <a name="multiple-forests-in-a-resource-forest-topology-with-hybrid-skype-for-business"></a>Varios bosques en una topología de bosque de recursos con una implementación híbrida de Skype Empresarial 
<a name="BKMK_multipleforestopology"> </a>

En este escenario, hay uno o más local bosques de usuarios, y se implementa en un bosque de recursos dedicado de Skype para la empresa y está configurado para el modo híbrido con Skype para profesionales en línea. Exchange Server puede ser instalados en servidores locales en el mismo bosque de recursos o de un bosque diferente y puede configurarse para implementación híbrida con Exchange Online. Como alternativa, pueden proporcionar servicios de correo electrónico exclusivamente por Exchange Online para las cuentas locales.
  
Para obtener más información, vea [Configure un entorno de varios bosque para entornos híbridos Skype para la empresa](../../skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/configure-a-multi-forest-environment-for-hybrid.md).
  
## <a name="domain-name-system-dns"></a>Sistema de nombre de dominio (DNS)
<a name="DNS"> </a>

Skype para Business Server 2015 requiere DNS, por los motivos siguientes:
  
- DNS permite Skype para Business Server 2015 detectar los servidores internos o grupos de servidores, lo que permite para las comunicaciones de servidor a servidor.
    
- DNS permite a cliente máquinas detectar el grupo de servidores Front-End o el servidor Standard Edition que se utiliza para las transacciones SIP.
    
- Asocia las direcciones URL sencillas para conferencias con los servidores que hospedan dichas conferencias.
    
- DNS permite a los usuarios externos y los equipos cliente para conectarse a los servidores perimetrales, o el proxy inverso HTTP, para la mensajería instantánea (IM) o conferencia.
    
- Comunicaciones unificadas (UC) permite detectar dispositivos que no están registrados en el grupo de servidores Front-End o un servidor Standard Edition que está ejecutando el servicio web de actualización de dispositivos para obtener actualizaciones y envíe los registros.
    
- El uso de DNS permitir que los clientes móviles detecten automáticamente recursos de servicios web sin que los usuarios tengan que escribir manualmente las direcciones URL en la configuración del dispositivo.
    
- También se usa para el equilibrado de carga DNS.
    
Es importante tener en cuenta que Skype para Business Server 2015 no admite nombres de dominio internacionalizados (IDN).
  
Y es extremadamente importante recordar que cualquier nombre en DNS ser idéntico al nombre de equipo configurado en cualquier servidor que usa Skype para Business Server 2015. En concreto, se no puede tener cualquier nombre de short en el entorno y deben tener nombres de dominio completos para el generador de topología.
  
Esto parece que sería lógico para cualquier equipo que se ha unido a un dominio, pero si tiene un servidor perimetral que no está unido a su dominio, puede tener un valor predeterminado de un nombre corto con ningún sufijo de dominio. Asegúrese de que no es el caso, en DNS o en el servidor perimetral o cualquier Skype para Business Server 2015 servidor o grupo de servidores, en realidad.
  
Y definitivamente no utilice caracteres Unicode o caracteres de subrayado. Los caracteres estándar (que son A-z, a-z, 0-9 y guiones) son los que se van a ser compatibles con el DNS externo y certificación pública (que necesitará para asignar nombres de dominio completos al nombre de sujeto en el certificado, no olvide), por lo que se va de repuesto usted mismo una gran cantidad de problemas si nombre teniendo esto en cuenta.
  
Si quiere más información sobre los requisitos de DNS para redes, consulte la sección [Networking](../../plan-your-deployment/network-requirements/network-requirements.md) de la documentación de planificación.
  
## <a name="certificates"></a>Certificados
<a name="Certs"> </a>

Unas de las cosas más importantes que puede hacer antes de la implementación es asegurarse de que sus certificados están en orden. Skype para Business Server 2015 necesita una infraestructura de clave pública (PKI) para el transporte layer security (TLS) y conexiones de seguridad (MTLS) de capa de transporte mutua. Básicamente, para comunicarse de forma segura en una forma estandarizada, Skype para Business Server utiliza certificados emitidos por entidades de certificación (CA).
  
Éstas son algunas de las cosas que Skype para Business Server 2015 utiliza certificados para:
  
- Conexiones TLS entre clientes y servidores
    
- Conexiones MTLS entre servidores
    
- Federación mediante la detección automática de DNS de socios
    
- Acceso de usuarios remotos a la mensajería instantánea (MI)
    
- Acceso de usuarios externos a sesiones de audio/vídeo (A/V), a uso compartido de aplicaciones y a conferencias
    
- Hablar con aplicaciones web y Outlook Web Access (OWA)
    
Por lo que la planificación de certificado s obligatorio. Ahora, vamos a examinar una lista de algunas de las cosas que debe tener en cuenta al solicitar certificados:
  
- Todos los certificados de servidor deben admitir la autorización de servidor (EKU de servidor).
    
- Todos los certificados de servidor deben contener un punto de distribución CRL (CDP).
    
- Todos los certificados deben estar firmados mediante un algoritmo de firma compatible con el sistema operativo. Skype para Business Server 2015 admite el SHA-1 y SHA-2 suite de síntesis de tamaños (224, 256, 384 y 512 bits) y cumple o supera los requisitos del sistema operativo.
    
- Se admite la inscripción automática para los servidores internos de Skype para Business Server 2015.
    
- No se admite la inscripción automática para Skype para los servidores perimetrales de Business Server 2015.
    
- Al enviar una solicitud de certificado basada en web para una entidad de certificación de Windows Server 2003, deberá hacerlo desde un equipo que ejecuta Windows Server 2003 con SP2 o Windows XP.
    
> [!NOTE]
> Aunque KB922706 ofrece soporte técnico para resolver problemas relacionados con los certificados web de inscripción de una inscripción web de los servicios de certificados de Windows Server 2003, no permite el uso de Windows Server 2008, Windows Vista o Windows 7 para solicitar un certificado desde una entidad de certificación de Windows Server 2003. 
  
> [!NOTE]
> No está permitido usar el algoritmo de firma RSASSA-PSS, ya que podría dar lugar a errores en problemas relacionados con el inicio de sesión y el desvío de llamadas, entre otros.  
  
- Se admiten longitudes de clave de cifrado de 1024, 2048 y 4096. Se recomienda usar longitudes de clave de 2048 y superiores.
    
- El algoritmo de firma hash o implícito predeterminado es RSA. También se admiten los algoritmos ECDH_P256, ECDH_P384 y ECDH_P521.
    
Por lo que es un lote pensar y definitivamente, hay una variedad de niveles de comodidad con solicitar certificados a una entidad de certificación. Le ofrecemos algunos consejos más detallados a continuación para realizar la planeación sea lo más sencillo como sea posible.
  
### <a name="certificates-for-your-internal-servers"></a>Certificados para los servidores internos

Necesitará certificados para la mayoría de los servidores internos, y es probable que se obtendrá de una CA interna (es decir, uno que se encuentra en el dominio). Si quiere, puede solicitar estos certificados a una CA externa (localizada en Internet). Si se pregunta qué entidad de certificación pública deben ir a, puede consultar la lista de [los socios de certificados de comunicaciones unificadas](https://support.microsoft.com/kb/929395/en-us) .
  
También va a necesitar certificados cuando Skype para Business Server 2015 se comunica con otras aplicaciones y servidores, como Microsoft Exchange Server. Obviamente, debe tratarse de certificados que estas otras aplicaciones y servidores admitan. Skype para Business Server 2015 y otros productos de Microsoft admite el protocolo Open Authorization (OAuth) para la autorización y autenticación de servidor a servidor. Si está interesado en esta, tenemos un artículo de planeación adicional para OAuth y Skype para Business Server 2015.
  
Skype para Business Server 2015 también incluye compatibilidad con (sin necesidad de) los certificados firmados con la función de algoritmo hash SHA-256. Para permitir el acceso externo mediante SHA-256, una entidad de certificación pública que usa SHA-256 emite el certificado externo.
  
Para probar y mantener las cosas sencilla, hemos los requisitos de certificado para los servidores Standard Edition, los grupos de servidores Front-End y otras funciones, en las tablas siguientes, con el ficticia contoso.com usada para ver ejemplos (que probablemente se van a usar algo Else para su entorno). Estos son todos los certificados de servidor web estándar, con las claves privadas que están no exportable. Aspectos adicionales que se tenga en cuenta:
  
- El uso mejorado de clave (EKU) del servidor se configura automáticamente al usar el asistente para certificados para solicitar certificados.
    
- El nombre descriptivo de cada certificado debe ser único en el almacén del equipo.
    
- Según los nombres de ejemplo que aparece a continuación, si ha configurado sipinternal.contoso.com o sipexternal.contoso.com en su DNS, deben agregarse a nombre de alternativa de sujeto del certificado (SAN).
    
Certificados para servidores Standard Edition:
  
|**Certificado**|**Nombre de sujeto/Nombre común**|**Nombre alternativo de sujeto**|**Ejemplo**|**Comentarios**|
|:-----|:-----|:-----|:-----|:-----|
|Predeterminado  <br/> |FQDN del grupo de servidores  <br/> |FQDN del grupo y FQDN del servidor  <br/> Si hay varios dominios SIP y está habilitada la configuración automática de los clientes, el Asistente para certificados detectará y agregará los FQDN de todos los dominios SIP admitidos.  <br/> Si este grupo de servidores es el servidor de inicio automático de sesión de los clientes y se requiere una correspondencia exacta del sistema de nombres de dominio (DNS) en la directiva del grupo, necesitará también entradas para sip.sipdomain (para cada uno de los dominios SIP que tenga).  <br/> |SN=se01.contoso.com; SAN=se01.contoso.com  <br/> Si este grupo de servidores es el servidor de inicio automático de sesión de los clientes y se requiere una correspondencia exacta de DNS en la directiva del grupo, necesitará también SAN=sip.contoso.com; SAN=sip.fabrikam.com  <br/> |En servidor de Standard Edition de los servidores Standard Edition, el FQDN del servidor es el mismo que el FQDN del grupo.  <br/> El asistente detecta todos los dominios SIP especificados durante la instalación y los agrega automáticamente al nombre alternativo de sujeto.  <br/> También puede usar este certificado para la autenticación de servidor a servidor.  <br/> |
|Web interno  <br/> |FQDN del servidor  <br/> |Cada uno de los siguientes elementos:  <br/> • Internal web FQDN (que es el mismo que el FQDN del servidor)  <br/> Y  <br/> • Direcciones URL sencillas de reunión  <br/> Dirección URL sencilla de • dial-in  <br/> • Dirección URL sencilla de administración  <br/> O BIEN  <br/> • Una entrada comodín para las direcciones URL sencillas  <br/> |SN=se01.contoso.com; SAN=se01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com; SAN=admin.contoso.com  <br/> Con un certificado de comodín:  <br/> SN=se01.contoso.com; SAN=se01.contoso.com; SAN =\*. contoso.com  <br/> |No se puede invalidar el FQDN en el generador de web interno.  <br/> Si dispone de varias URL sencillas de reunión, deberá incluirlas todas como nombres alternativos de sujeto.  <br/> Las entradas de comodín se admiten para las entradas de direcciones URL sencillas.  <br/> |
|Web externo  <br/> |FQDN del servidor  <br/> |Cada uno de los siguientes elementos:  <br/> • FQDN de web externo  <br/> Y  <br/> Dirección URL sencilla de • dial-in  <br/> • Cumplir con las direcciones URL sencillas por dominio SIP  <br/> O BIEN  <br/> • Una entrada comodín para las direcciones URL sencillas  <br/> |SN=se01.contoso.com; SAN=webcon01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com  <br/> Con un certificado de comodín:  <br/> SN=se01.contoso.com; SAN=webcon01.contoso.com; SAN =\*. contoso.com  <br/> |Si tiene varias URL simples de reunión, tiene que incluir todos ellos como nombres alternativos del sujeto.  <br/> Las entradas de comodín se admiten para las entradas de direcciones URL sencillas.  <br/> |
   
Certificados para servidores Front-End de un grupo de servidores Front-End:
  
|**Certificado**|**Nombre de sujeto/Nombre común**|**Nombre alternativo de sujeto**|**Ejemplo**|**Comentarios**|
|:-----|:-----|:-----|:-----|:-----|
|Predeterminado  <br/> |FQDN del grupo de servidores  <br/> |FQDN del grupo y FQDN del servidor  <br/> Si hay varios dominios SIP y está habilitada la configuración automática de los clientes, el Asistente para certificados detectará y agregará los FQDN de todos los dominios SIP admitidos.  <br/> Si este grupo de servidores es el servidor de inicio automático de sesión de los clientes y se requiere una correspondencia exacta del sistema de nombres de dominio (DNS) en la directiva del grupo, necesitará también entradas para sip.sipdomain (para cada uno de los dominios SIP que tenga).  <br/> |SN=eepool.contoso.com; SAN=eepool.contoso.com; SAN=ee01.contoso.com   <br/> Si este grupo de servidores es el servidor de inicio automático de sesión de los clientes y se requiere una correspondencia exacta de DNS en la directiva del grupo, necesitará también SAN=sip.contoso.com; SAN=sip.fabrikam.com  <br/> |El asistente detecta todos los dominios SIP especificados durante la instalación y los agrega automáticamente al nombre alternativo de sujeto.  <br/> También puede usar este certificado para la autenticación de servidor a servidor.  <br/> |
|Web interno  <br/> |FQDN del grupo de servidores  <br/> |Cada uno de los siguientes elementos:  <br/> • Internal web FQDN (que no es el mismo que el FQDN del servidor)  <br/> FQDN del servidor •  <br/> • Skype para el FQDN del grupo de negocio  <br/> Y  <br/> • Direcciones URL sencillas de reunión  <br/> Dirección URL sencilla de • dial-in  <br/> • Dirección URL sencilla de administración  <br/> O BIEN  <br/> • Una entrada comodín para las direcciones URL sencillas  <br/> |SN=ee01.contoso.com; SAN=ee01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com; SAN=admin.contoso.com  <br/> Con un certificado de comodín:  <br/> SN=ee01.contoso.com; SAN=ee01.contoso.com; SAN =\*. contoso.com  <br/> |Si tiene varias URL simples de reunión, tiene que incluir todos ellos como nombres alternativos del sujeto.  <br/> Las entradas de comodín se admiten para las entradas de direcciones URL sencillas.  <br/> |
|Web externo  <br/> |FQDN del grupo de servidores  <br/> |Cada uno de los siguientes elementos:  <br/> • FQDN de web externo  <br/> Y  <br/> Dirección URL sencilla de • dial-in  <br/> • Dirección URL sencilla de administración  <br/> O BIEN  <br/> • Una entrada comodín para las direcciones URL sencillas  <br/> |SN=ee01.contoso.com; SAN=webcon01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com  <br/> Con un certificado de comodín:  <br/> SN=ee01.contoso.com; SAN=webcon01.contoso.com; SAN =\*. contoso.com  <br/> |Si tiene varias URL simples de reunión, tiene que incluir todos ellos como nombres alternativos del sujeto.  <br/> Las entradas de comodín se admiten para las entradas de direcciones URL sencillas.  <br/> |
   
Certificados para el Director:
  
|**Certificado**|**Nombre de sujeto/Nombre común**|**Nombre alternativo de sujeto**|**Ejemplo**|
|:-----|:-----|:-----|:-----|
|Valor predeterminado  <br/> |Grupo de directores  <br/> |FQDN del Director, FQDN del grupo de servidores Director.  <br/> Si este grupo de servidores es el servidor de inicio de sesión automático para los clientes y exacta de DNS requiere una directiva de grupo, necesitará también entradas para sip.sipdomain (para cada dominio SIP que tiene).  <br/> |pool.contoso.com; SAN=dir01.contoso.com   <br/> Si este grupo de servidores de Director es el servidor de inicio de sesión automático para los clientes y exacta de DNS es necesario en la directiva de grupo, necesitará también SAN; SAN=SIP.fabrikam.com  <br/> |
|Web interno  <br/> |FQDN del servidor  <br/> |Cada uno de los siguientes elementos:  <br/> • Internal web FQDN (que es el mismo que el FQDN del servidor)  <br/> FQDN del servidor •  <br/> • Skype para el FQDN del grupo de negocio  <br/> Y  <br/> • Direcciones URL sencillas de reunión  <br/> Dirección URL sencilla de • dial-in  <br/> • Dirección URL sencilla de administración  <br/> O BIEN  <br/> • Una entrada comodín para las direcciones URL sencillas  <br/> |SN=dir01.contoso.com; SAN=dir01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com; SAN=admin.contoso.com  <br/> Con un certificado de comodín:  <br/> SN=dir01.contoso.com; SAN=dir01.contoso.com SAN =\*. contoso.com  <br/> |
|Web externo  <br/> |FQDN del servidor  <br/> |Cada uno de los siguientes elementos:  <br/> • FQDN de web externo  <br/> Y  <br/> • Cumplir con las direcciones URL sencillas por dominio SIP  <br/> Dirección URL sencilla de • dial-in  <br/> O BIEN  <br/> • Una entrada comodín para las direcciones URL sencillas  <br/> |El FQDN de web externo de Director debe ser distinto del grupo de servidores Front-End o un servidor Front-End.  <br/> SN=dir01.contoso.com; SAN=directorwebcon01.contoso.com SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com  <br/> Con un certificado de comodín:  <br/> SN=dir01.contoso.com; SAN=directorwebcon01.contoso.com SAN =\*. contoso.com  <br/> |
   
Certificados para el servidor de mediación independiente:
  
|**Certificado**|**Nombre de sujeto/Nombre común**|**Nombre alternativo de sujeto**|**Ejemplo**|
|:-----|:-----|:-----|:-----|
|Valor predeterminado  <br/> |FQDN del grupo de servidores  <br/> |FQDN del grupo de servidores  <br/> FQDN del miembro del grupo de servidores  <br/> |SN=medsvr-pool.contoso.net; SAN=medsvr-pool.contoso.net; SAN=medsvr01.contoso.net  <br/> |
   
Certificados para la aplicación de sucursal con funciones de supervivencia:
  
|**Certificado**|**Nombre de sujeto/Nombre común**|**Nombre alternativo de sujeto**|**Ejemplo**|
|:-----|:-----|:-----|:-----|
|Predeterminado  <br/> |FQDN de la aplicación  <br/> |SIP. \<sipdomain\> (necesita sólo una entrada por dominio SIP)  <br/> |SN=sba01.contoso.net; SAN=sip.contoso.com; SAN=sip.fabrikam.com  <br/> |
   
### <a name="certificates-for-your-persistent-chat-server"></a>Certificados para el servidor de chat persistente

Al instalar al servidor de Chat persistente, va a necesitar un certificado emitido por la misma entidad de certificación que el utilizado por su Skype para los servidores internos Business Server 2015. Esto debe realizarse para cada servidor que ejecuta el Persistent Chat Web Services para carga y descarga de archivos. Se recomienda encarecidamente tiene los certificados necesarios antes de iniciar la instalación de Chat persistente, y si la entidad de certificación es externo, es así incluso más (estas cosas pueden tardar un poco de tiempo que ser emitidos).
  
### <a name="certificates-for-external-user-access-edge"></a>Certificados para el acceso de usuarios externos (Edge)

Skype para Business Server 2015 admite el uso de un **solo certificado público** para interfaces externas del borde de conferencia de web y de acceso, además de la A y servicio de autenticación de V, que se proporciona a través de los servidores perimetrales. La interfaz perimetral interna normalmente utiliza un certificado privado emitido por la entidad de certificación interna, pero si lo prefiere, puede usar un certificado público para esto también, si procede de una entidad de certificación de confianza.
  
Su proxy inverso (RP) también usa un certificado público y cifra sus propias comunicaciones con los clientes y los servidores internos mediante HTTP (o, para ser más precisos, TLS por HTTP).
  
### <a name="certificates-for-mobility"></a>Certificados para movilidad

Si va a implementar movilidad y está fomentando la detección automática para clientes móviles, va a necesitar incluir algunas entradas de nombre alternativo de sujeto adicional en los certificados para admitir las conexiones seguras de los clientes móviles.
  
¿Qué certificados? Necesitará nombres de SAN para la detección automática en los certificados aquí:
  
- Grupo de directores
    
- Grupo de servidores front-end
    
- Proxy inverso
    
En las siguientes tablas se ofrecen detalles.
  
Ahora, esto es donde previamente un poco de planeación es bueno, pero a veces que ha implementado Skype para Business Server 2015 sin que tengan la intención de implementar la movilidad y que aparece la línea hacia abajo cuando ya tiene certificados en el entorno. Volver a emitir los certificados desde una CA interna suele ser sencillo, pero en el caso de una CA pública puede resultar un poco más caro.
  
Si eso es lo que está viendo, y si tiene una gran cantidad de dominios SIP (que provocará que la adición de SAN más costoso), puede configurar el proxy inverso para usar HTTP para la solicitud inicial de Autodiscover Service, en lugar de usar HTTPS (que es el valor predeterminado configuración). Tiene más información en el tema Planificación para la movilidad.
  
Requisitos de certificado de grupo de directores y grupo de servidores Front-End:
  
|**Descripción**|**Entrada SAN**|
|:-----|:-----|
|URL del servicio Detección automática interna  <br/> |SAN = lyncdiscoverinternal. \<sipdomain\>  <br/> |
|URL del servicio Detección automática externa  <br/> |SAN = lyncdiscover. \<sipdomain\>  <br/> |
   
Como alternativa, puede usar SAN =\*. \<sipdomain\>
  
Requisitos de certificado (CA pública) de proxy inverso
  
|**Descripción**|**Entrada SAN**|
|:-----|:-----|
|URL del servicio Detección automática externa  <br/> |SAN = lyncdiscover. \<sipdomain\>  <br/> |
   
Este SAN debe asignarse al certificado asignado al agente de escucha SSL de su proxy inverso.
  
> [!NOTE]
> Curso de su proxy inverso del agente de escucha tener SANs para sus direcciones de URL de servicios Web externos. Algunos ejemplos serían SAN=skypewebextpool01.contoso.com y dirwebexternal.contoso.com, si ha implementado el Director, (que es opcional). 
  
## <a name="file-share"></a>Recurso compartido de archivos
<a name="Fileshare"> </a>

Skype para Business Server 2015 es capaz de utilizar el mismo recurso compartido de archivos para el almacenamiento de todos los archivos. Deberá tener en cuenta lo siguiente:
  
- Un recurso compartido de archivos debe estar en un almacenamiento conectado directo (DAS) o en un almacenamiento en red (SAN), y esto incluye el sistema de archivos distribuidos (DFS) y las matrices redundantes de discos independientes (RAID). Para obtener más información sobre DFS para Windows Server 2012, desproteger [esta página DFS](https://technet.microsoft.com/en-us/library/jj127250.aspx).
    
- Se recomienda un clúster compartido para el recurso compartido de archivos. Si está utilizando uno, debe organizar en clústeres Windows Server 2012 o Windows Server 2012 R2. Windows Server 2008 R2 también es aceptable. ¿Por qué el más reciente para Windows? Las versiones más antiguas no pueden tener los permisos adecuados para habilitar todas las características. Puede usar el Administrador de clústeres para crear los recursos compartidos de archivos y, en este artículo [cómo crear recursos compartidos de archivos en un clúster](https://support.microsoft.com/en-us/help/224967/how-to-create-file-shares-on-a-cluster) le ayudará con esos detalles.
    
> [!CAUTION] 
> Es preciso que recuerde que no se admite el uso del almacenamiento conectado a la red (NAS) como recurso compartido de archivo, de modo que utilice una de las opciones que se han descrito anteriormente. 
  

