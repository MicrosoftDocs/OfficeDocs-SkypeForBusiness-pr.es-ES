---
title: Requisitos del entorno para Skype Empresarial Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/15/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 4812c444-2546-48d7-9ca7-b71fce508ed8
description: 'Resumen: Configure los requisitos que no son de servidor para Skype empresarial Server 2015. Hay una variedad de cosas que desea configurar antes de realizar la implementación, como Active Directory, DNS, Certs y Fileshares.'
ms.openlocfilehash: 7af4587dfef237a6449dbfa9a271910398ec8a41
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41801910"
---
# <a name="environmental-requirements-for-skype-for-business-server-2015"></a>Environmental requirements for Skype for Business Server 2015
 
**Resumen:** Configure los requisitos que no son de servidor para Skype empresarial Server 2015. Hay una variedad de cosas que desea configurar antes de realizar la implementación, como Active Directory, DNS, Certs y Fileshares.
  
¿Qué es un requisito medioambiental para Skype empresarial Server 2015? Bueno, hemos colocado todo lo que no está directamente relacionado con este tema, por lo que no tiene que hacer clic en él. Si está buscando requisitos previos del servidor, puede consultar los [requisitos del servidor para Skype empresarial Server 2015](server-requirements.md) doc. la[planeación de redes](../../plan-your-deployment/network-requirements/network-requirements.md) también está documentada por separado. De lo contrario, esto es lo que tenemos en este artículo:
  
- [Active Directory](environmental-requirements.md#AD)
  
- [Sistema de nombre de dominio (DNS)](environmental-requirements.md#DNS)
  
- [Certificados](environmental-requirements.md#Certs)
  
- [Recurso compartido de archivos](environmental-requirements.md#Fileshare)
  
## <a name="active-directory"></a>Active Directory
<a name="AD"> </a>

Mientras que un gran número de datos de configuración para servidores y servicios se almacenan en el almacén de administración central de Skype empresarial Server 2015, hay algunas cosas aún almacenadas en Active Directory:
  
|**Objetos de Active Directory**|**Tipos de objeto**|
|:-----|:-----|
|Extensiones de esquema  <br/> |Extensiones de objetos de usuario  <br/> |
||Extensiones de Lync Server 2013 y Lync Server 2010 para mantener la compatibilidad con las versiones compatibles anteriores.  <br/> |
|Datos  <br/> |URI de SIP del usuario y otros parámetros de usuario  <br/> |
||Objetos de contacto para aplicaciones (como la aplicación de grupo de respuesta y la aplicación de operador de conferencia).  <br/> |
||Datos publicados para lograr compatibilidad con versiones anteriores  <br/> |
||Un punto de control de servicio (SCP) para el almacén de administración central.  <br/> |
||Cuenta de autenticación Kerberos (un objeto de equipo opcional)  <br/> |
   
### <a name="os-for-domain-controllers"></a>SO para controladores de dominio

¿Qué SO de controladores de dominio se pueden usar? Tenemos la siguiente lista:

- Windows Server 2019 (debe tener la actualización acumulativa 5 o posterior de Skype empresarial Server 2015)
  
- Windows Server 2016
    
- Windows Server 2012 R2
    
- Windows Server 2012
    
- Windows Server 2008 R2
    
- Windows Server 2008
    
Ahora, el nivel funcional de dominio de cualquier dominio en el que se implemente Skype empresarial Server 2015 y el nivel funcional de bosque de cualquier bosque en el que se implemente Skype empresarial Server 2015 debe ser uno de los siguientes:

- Windows Server 2019 (debe tener la actualización acumulativa 5 o posterior de Skype empresarial Server 2015)
  
- Windows Server 2016
    
- Windows Server 2012 R2
    
- Windows Server 2012
    
- Windows Server 2008 R2
    
- Windows Server 2008
    
- Windows Server 2003
    
¿Puede haber controladores de dominio de solo lectura en estos entornos? Sí, mientras haya también disponible un controlador de dominio de escritura.
  
Ahora, es importante saber que Skype empresarial Server 2015 no es compatible con los dominios con etiqueta única. ¿Qué son? Si tiene un dominio raíz con la etiqueta contoso. local, eso será adecuado. Si tiene un dominio raíz que simplemente tiene el nombre local, eso no funcionará y no se admitirá como resultado. Un poco más sobre esto se ha escrito [en este artículo de Knowledge Base](https://support.microsoft.com/kb/300684/en-us).
  
Skype empresarial Server 2015 tampoco permite cambiar el nombre de los dominios. Si realmente lo ha hecho, tendrá que desinstalar Skype empresarial Server 2015, realizar el cambio de nombre de dominio y, a continuación, volver a instalar Skype empresarial Server 2015.
  
Por último, es posible que esté tratando con un dominio con un entorno de AD DS bloqueado y eso es todo bien. Tenemos más información sobre cómo implementar Skype empresarial Server 2015 en ese tipo de entorno en los documentos de implementación.
  
### <a name="ad-topologies"></a>Topologías de AD

Las topologías compatibles de Skype empresarial Server 2015 son:
  
- Un solo bosque con un solo dominio
    
- Un solo bosque con un solo árbol y varios dominios
    
- Un solo bosque con varios árboles y espacios de nombres separados
    
- Varios bosques en una topología de bosque central
    
- Varios bosques en una topología de bosque de recursos
    
- Varios bosques en una topología de bosque de recursos de Skype Empresarial con Exchange Online
    
- Varios bosques en una topología de bosque de recursos con Skype Empresarial Online y Azure Active Directory Connect
    
Disponemos de diagramas y descripciones para ayudarle a determinar qué topología tiene en su entorno o lo que necesita configurar antes de instalar Skype empresarial Server 2015. Para que sea simple, también incluimos una clave:
  
![Leyenda de los iconos usados en los diagramas de topología de Skype Empresarial](../../media/cc0dbc17-cf81-4b79-bf99-4614cc6828a0.png)
  
#### <a name="single-forest-with-single-domain"></a>Un solo bosque con un solo dominio

![Diagrama de un solo bosque de Active Directory con un único dominio](../../media/24921a0b-3a3e-4bad-8427-49300e2e3f7a.png)
  
No es más fácil que esto, es un bosque de dominio único, es una topología común.
  
#### <a name="single-forest-with-a-single-tree-and-multiple-domains"></a>Un solo bosque con un solo árbol y varios dominios

![Diagrama de un solo bosque con un único árbol y varios dominios](../../media/63b9f0dd-6bac-4ba9-ae68-8be032d09dcb.png)
  
Este diagrama incluye también un único bosque, pero tiene también uno o más dominios secundarios (tres, en este ejemplo concreto). Por lo tanto, el dominio en el que se crean los usuarios puede ser diferente del dominio en el que se implementa Skype empresarial Server 2015. ¿Por qué esto es importante? Es importante recordar que al implementar un grupo de servidores front-end de Skype empresarial Server, todos los servidores de ese grupo deben estar en un solo dominio. Puede tener administración de dominios interrelacionados con el soporte técnico de los grupos de administración universal de Windows de Skype empresarial Server.
  
Volver al diagrama anterior, puede ver que los usuarios de un dominio pueden obtener acceso a los grupos de servidores de Skype empresarial desde el mismo dominio o desde diferentes dominios, incluso si esos usuarios están en un dominio secundario.
  
#### <a name="single-forest-with-multiple-trees-and-disjoint-namespaces"></a>Un solo bosque con varios árboles y espacios de nombres separados

![Diagrama de un solo bosque con varios árboles y espacios de nombres separados](../../media/5ede77a1-f5d2-499c-a2c8-d02f3c2f7cd7.png)
  
Es posible que tenga una topología similar a la de este diagrama, en la que tiene un bosque, pero dentro de ese bosque hay varios dominios, con espacios de nombres independientes de AD. En ese caso, este diagrama es una buena ilustración, ya que tenemos usuarios en tres dominios diferentes que tienen acceso a Skype empresarial Server 2015. Las líneas continuas indican que acceden a un grupo de servidores de Skype empresarial en su propio dominio, mientras que una línea discontinua indica que va a un grupo en un árbol diferente.
  
Como puede verse, todos los usuarios pueden acceder a los grupos, ya estén en el mismo dominio, en el mismo árbol o en un árbol diferente.
  
#### <a name="multiple-forests-in-a-central-forest-topology"></a>Varios bosques en una topología de bosque central

![Diagrama de varios bosques en una topología de bosque central](../../media/fec40746-4254-4c84-86b9-aad4a616ea2f.png)
  
Skype empresarial Server 2015 admite varios bosques configurados en una topología de bosque central. Si no está seguro de lo que tiene, el bosque central de la topología usa objetos en él para representar a los usuarios de otros bosques y hospeda cuentas de usuario para cualquier usuario del bosque.
  
¿Cómo funciona? Bueno, un producto de sincronización de directorios (como Forefront Identity Manager o FIM) administra las cuentas de usuario de su organización durante su existencia. Cuando una cuenta se crea o elimina en un bosque, este cambio se sincroniza con el contacto correspondiente en el bosque central.
  
Evidentemente, si tu infraestructura de AD está en el lugar de esta topología, es posible que no sea fácil, pero si ya estás allí o si aún no estás pensando en la infraestructura de tu bosque, esta puede ser una buena opción. Puede centralizar la implementación de Skype empresarial Server 2015 dentro de un único bosque, mientras los usuarios pueden buscar, comunicar y ver la presencia de otros usuarios en cualquier bosque. Todas las actualizaciones de contactos de usuarios se gestionan automáticamente con el software de sincronización.
  
#### <a name="multiple-forests-in-a-skype-for-business-resource-forest-topology"></a>Varios bosques en una topología de bosque de recursos de Skype Empresarial
<a name="BKMK_multipleforestopology"> </a>

![Diagrama de varios bosques en una topología de bosque de recursos](../../media/41efa3b6-d9e6-47df-992b-fefcfc39a80d.png)
  
También se admite una topología de bosque de recursos; es donde un bosque está dedicado a ejecutar las aplicaciones de servidor, como Microsoft Exchange Server y Skype empresarial Server 2015. Estos bosques de recursos también hospedan una representación sincronizada de objetos de usuario activos, pero no tienen cuentas de usuario habilitadas para el inicio de sesión. Por lo tanto, el bosque de recursos es un entorno de servicios compartidos para otros bosques en el que residen los objetos de usuario y tienen una relación de confianza de nivel de bosque con el bosque de recursos.
  
Tenga en cuenta que Exchange Server puede implementarse en el mismo bosque de recursos que Skype empresarial Server o en un bosque diferente.
  
Para implementar Skype empresarial Server 2015 en este tipo de topología, debe crear un objeto de usuario deshabilitado en el bosque de recursos para cada cuenta de usuario en los bosques de usuario (si Microsoft Exchange Server ya está en el entorno, esto podría hacerse por usted). A continuación, necesitará una herramienta de sincronización de directorios (como Forefront Identity Manager o FIM) para administrar las cuentas de usuario a través de su ciclo de vida.
  
#### <a name="multiple-forests-in-a-skype-for-business-resource-forest-topology-with-exchange-online"></a>Varios bosques en una topología de bosque de recursos de Skype Empresarial con Exchange Online
<a name="BKMK_multipleforestopology"> </a>

Esta topología es similar a la descrita en [Varios bosques en una topología de bosque de recursos de Skype Empresarial](environmental-requirements.md#BKMK_multipleforestopology).
  
En esta topología, hay uno o varios bosques de usuarios y Skype empresarial Server se implementa en un bosque de recursos dedicado. Exchange Server se puede implementar en el entorno local en el mismo bosque de recursos o en un bosque diferente y configurar para un híbrido con Exchange Online, o los servicios de correo electrónico solo los puede proporcionar Exchange Online para las cuentas locales. No existe ningún diagrama disponible para esta topología.
  
#### <a name="multiple-forests-in-a-resource-forest-topology-with-skype-for-business-online-and-azure-active-directory-connect"></a>Varios bosques en una topología de bosque de recursos con Skype Empresarial Online y Azure Active Directory Connect
<a name="BKMK_multipleforestopology"> </a>

![Muestra dos bosques de AD, uno de usuario y uno de recurso. Ambos bosques tienen una relación de confianza y se sincronizan con Office 365 mediante Azure AD Connect. Todos los usuarios se habilitan para Skype Empresarial a través de Office 365.](../../media/6d54558d-8786-4ebf-90f6-55ae3fdb5ae7.jpg)
  
Con este escenario, hay varios bosques locales, con una topología de bosque de recursos. Hay una relación de total confianza entre los bosques de Active Directory. La herramienta Azure Active Directory Connect se utiliza para sincronizar cuentas entre los bosques de usuarios locales y Office 365.
  
 La organización también tiene Office 365 y usa [Azure Active Directory Connect](https://go.microsoft.com/fwlink/p/?LinkId=614836) para sincronizar sus cuentas locales con Office 365. Los usuarios habilitados para Skype empresarial se habilitan a través de Office 365 y Skype empresarial online. Skype empresarial Server no está implementado localmente.
  
La autenticación de inicio de sesión único la proporciona una granja de servicios de Federación de Active Directory que se encuentra en el bosque de usuario.
  
En este escenario, se admite la implementación de Exchange local, Exchange Online, una solución híbrida de Exchange o no implementar Exchange. (El diagrama muestra solo Exchange local, pero las otras soluciones para Exchange también son totalmente compatibles).
  
#### <a name="multiple-forests-in-a-resource-forest-topology-with-hybrid-skype-for-business"></a>Varios bosques en una topología de bosque de recursos con una implementación híbrida de Skype Empresarial 
<a name="BKMK_multipleforestopology"> </a>

En este escenario, hay uno o varios bosques de usuarios locales, y Skype empresarial se implementa en un bosque de recursos dedicado y está configurado para el modo híbrido con Skype empresarial online. Exchange Server se puede implementar en el entorno local en el mismo bosque de recursos o en un bosque diferente, y se puede configurar para una implementación híbrida con Exchange Online. Como alternativa, Exchange Online puede proporcionar exclusivamente los servicios de correo electrónico para las cuentas locales.
  
Para obtener más información, vea [configurar un entorno de varios bosques para una implementación híbrida de Skype empresarial](../../skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/configure-a-multi-forest-environment-for-hybrid.md).
  
## <a name="domain-name-system-dns"></a>Sistema de nombre de dominio (DNS)
<a name="DNS"> </a>

Skype empresarial Server 2015 requiere DNS, por los siguientes motivos:
  
- DNS permite que Skype empresarial Server 2015 detecte servidores o grupos de servidores internos, lo que permite la comunicación entre servidores.
    
- DNS permite que los equipos cliente descubran el grupo de servidores front-end o el servidor Standard Edition que se usa para las transacciones SIP.
    
- Asocia las direcciones URL sencillas para conferencias con los servidores que hospedan dichas conferencias.
    
- DNS permite que los usuarios externos y los equipos cliente se conecten a los servidores perimetrales, o el proxy inverso HTTP, para mensajería instantánea (mi) o conferencias.
    
- Permite que los dispositivos de comunicaciones unificadas (UC) que no estén registrados en descubran el grupo de servidores front-end o el servidor Standard Edition que ejecuta el servicio Web de actualización de dispositivos para obtener actualizaciones y enviar registros.
    
- El uso de DNS permitir que los clientes móviles detecten automáticamente recursos de servicios web sin que los usuarios tengan que escribir manualmente las direcciones URL en la configuración del dispositivo.
    
- También se usa para el equilibrado de carga DNS.
    
Es importante tener en cuenta que Skype empresarial Server 2015 no admite nombres de dominio internacionalizados (IDNs).
  
Además, es muy importante recordar que cualquier nombre en DNS es idéntico al nombre de equipo configurado en cualquier servidor usado por Skype empresarial Server 2015. En concreto, no podemos tener ningún nombre corto en el entorno y deben tener FQDN para el generador de topología.
  
Es como si fuera lógico para cualquier equipo ya unido a un dominio, pero si tienes un servidor perimetral que no está unido a tu dominio, puede tener un valor predeterminado con un nombre corto, sin un sufijo de dominio. Asegúrese de que no es así, ya sea en DNS o en el servidor perimetral, o en cualquier servidor o grupo de servidores de Skype empresarial Server 2015.
  
Y no usar definitivamente caracteres Unicode o de subrayado. Los caracteres estándar (que son a-Z, a-z, 0-9 y guiones) son aquellos que serán admitidos por entidades de certificación públicas y DNS externas (tendrá que asignar FQDN al SN en el certificado, no se olvide), por lo que le hará un montón de Grief si te asignaremos un nombre.
  
Si quiere más información sobre los requisitos de DNS para redes, consulte la sección [Networking](../../plan-your-deployment/network-requirements/network-requirements.md) de la documentación de planificación.
  
## <a name="certificates"></a>Certificados
<a name="Certs"> </a>

Unas de las cosas más importantes que puede hacer antes de la implementación es asegurarse de que sus certificados están en orden. Skype empresarial Server 2015 necesita una infraestructura de clave pública (PKI) para las conexiones de seguridad de la capa de transporte (TLS) y de seguridad de la capa de transporte mutuo (MTLS). Básicamente, para comunicarse con seguridad de forma estandarizada, Skype empresarial Server usa certificados emitidos por entidades de certificación (CA).
  
Estas son algunas de las cosas que Skype empresarial Server 2015 usa certificados para:
  
- Conexiones TLS entre clientes y servidores
    
- Conexiones MTLS entre servidores
    
- Federación mediante la detección automática de DNS de socios
    
- Acceso de usuarios remotos a la mensajería instantánea (MI)
    
- Acceso de usuarios externos a sesiones de audio/vídeo (A/V), a uso compartido de aplicaciones y a conferencias
    
- Hablar con aplicaciones web y Outlook Web Access (OWA)
    
Así que la planificación de certificados es imprescindible. Ahora, echemos un vistazo a una lista de algunas de las cosas que debe tener en cuenta al solicitar certificados:
  
- Todos los certificados de servidor deben admitir la autorización de servidor (EKU de servidor).
    
- Todos los certificados de servidor deben contener un punto de distribución CRL (CDP).
    
- Todos los certificados deben estar firmados mediante un algoritmo de firma compatible con el sistema operativo. Skype empresarial Server 2015 admite el conjunto de tamaños de compendio SHA-1 y SHA-2 (224, 256, 384 y 512 bits), y cumple o supera los requisitos del sistema operativo.
    
- La inscripción automática es compatible con los servidores internos que ejecutan Skype empresarial Server 2015.
    
- La inscripción automática no es compatible con los servidores perimetrales de Skype empresarial Server 2015.
    
- Al enviar una solicitud de certificado basada en Web a una CA de Windows Server 2003, debe enviarla desde un equipo con Windows Server 2003 con SP2 o Windows XP.
    
> [!NOTE]
> Aunque KB922706 ofrece soporte técnico para resolver problemas relacionados con los certificados web de inscripción de una inscripción web de los servicios de certificados de Windows Server 2003, no permite el uso de Windows Server 2008, Windows Vista o Windows 7 para solicitar un certificado desde una entidad de certificación de Windows Server 2003. 
  
> [!NOTE]
> No está permitido usar el algoritmo de firma RSASSA-PSS, ya que podría dar lugar a errores en problemas relacionados con el inicio de sesión y el desvío de llamadas, entre otros.  

> [!NOTE]
> Skype empresarial Server 2015 no admite certificados CNG.
  
- Se admiten longitudes de clave de cifrado de 1024, 2048 y 4096. Se recomienda usar longitudes de clave de 2048 y superiores.
    
- El algoritmo de firma hash o implícito predeterminado es RSA. También se admiten los algoritmos ECDH_P256, ECDH_P384 y ECDH_P521.
    
Así que es mucho para pensar y, definitivamente, hay una variedad de niveles de comodidad con la solicitud de certificados a una entidad de certificación. A continuación, le daremos algunas instrucciones adicionales para que su planificación sea tan fácil como sea posible.
  
### <a name="certificates-for-your-internal-servers"></a>Certificados para los servidores internos

Necesitará certificados para la mayoría de los servidores internos y lo más probable es que los obtenga de una entidad emisora de certificados interna (que se encuentra en un dominio). Si quiere, puede solicitar estos certificados a una CA externa (localizada en Internet). Si está preguntando qué entidad de certificación pública debe ir, puede consultar la lista de [socios de certificados de comunicaciones unificadas](/SkypeForBusiness/certification/services-ssl) .
  
También va a necesitar certificados cuando Skype empresarial Server 2015 se comunique con otras aplicaciones y servidores, como Microsoft Exchange Server. Obviamente, debe tratarse de certificados que estas otras aplicaciones y servidores admitan. Skype empresarial Server 2015 y otros productos de Microsoft son compatibles con el protocolo de autorización abierta (OAuth) para la autenticación y la autorización de servidor a servidor. Si está interesado en ello, tenemos un artículo de planeación adicional para OAuth y Skype empresarial Server 2015.
  
Skype empresarial Server 2015 también incluye compatibilidad con certificados (sin requerir) firmados con la función de hash criptográfica SHA-256. Para permitir el acceso externo mediante SHA-256, una entidad de certificación pública que usa SHA-256 emite el certificado externo.
  
Para probar y mantener las cosas de forma sencilla, hemos puesto los requisitos de los certificados para servidores Standard Edition, grupos de aplicaciones para el usuario y otras funciones, en las siguientes tablas, con el contoso.com ficticio que se usa para ejemplos (probablemente usará algo más para su entorno). Estos son todos los certificados de servidor web estándar, con claves privadas que no se pueden exportar. Algunas consideraciones adicionales que se deben tener en cuenta:
  
- El uso mejorado de clave (EKU) del servidor se configura automáticamente al usar el asistente para certificados para solicitar certificados.
    
- El nombre descriptivo de cada certificado debe ser único en el almacén del equipo.
    
- Según los nombres de ejemplo siguientes, si ha configurado sipinternal.contoso.com o sipexternal.contoso.com en su DNS, deberán agregarse al nombre alternativo de asunto (SAN) del certificado.
    
Certificados para servidores Standard Edition:
  
|**Certificado**|**Nombre de sujeto/Nombre común**|**Nombre alternativo de sujeto**|**Ejemplo**|**Comentarios**|
|:-----|:-----|:-----|:-----|:-----|
|Predeterminado  <br/> |FQDN del grupo de servidores  <br/> |FQDN del grupo y FQDN del servidor  <br/> Si hay varios dominios SIP y está habilitada la configuración automática de los clientes, el Asistente para certificados detectará y agregará los FQDN de todos los dominios SIP admitidos.  <br/> Si este grupo de servidores es el servidor de inicio automático de sesión de los clientes y se requiere una correspondencia exacta del sistema de nombres de dominio (DNS) en la directiva del grupo, necesitará también entradas para sip.sipdomain (para cada uno de los dominios SIP que tenga).  <br/> |SN=se01.contoso.com; SAN=se01.contoso.com  <br/> Si este grupo de servidores es el servidor de inicio automático de sesión de los clientes y se requiere una correspondencia exacta de DNS en la directiva del grupo, necesitará también SAN=sip.contoso.com; SAN=sip.fabrikam.com  <br/> |En el servidor Standard Edition servidores Standard Edition, el FQDN del servidor es el mismo que el FQDN del grupo.  <br/> El asistente detecta todos los dominios SIP especificados durante la instalación y los agrega automáticamente al nombre alternativo de sujeto.  <br/> También puede usar este certificado para la autenticación de servidor a servidor.  <br/> |
|Web interno  <br/> |FQDN del servidor  <br/> |Cada uno de los siguientes elementos:  <br/> • FQDN de la web interna (que es el mismo que el FQDN del servidor)  <br/> Y  <br/> • Cumplir con direcciones URL simples  <br/> • Dirección URL de acceso telefónico simple  <br/> • Dirección URL simple de administración  <br/> O BIEN  <br/> • Una entrada comodín para las direcciones URL simples  <br/> |SN=se01.contoso.com; SAN=se01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com; SAN=admin.contoso.com  <br/> Con un certificado de comodín:  <br/> SN = SE01. contoso. com; SAN = SE01. contoso. com; SAN =\*. contoso.com  <br/> |No puede invalidar el FQDN de la web interna en el generador de topología.  <br/> Si dispone de varias URL sencillas de reunión, deberá incluirlas todas como nombres alternativos de sujeto.  <br/> Las entradas de comodín se admiten para las entradas de direcciones URL sencillas.  <br/> |
|Web externo  <br/> |FQDN del servidor  <br/> |Cada uno de los siguientes elementos:  <br/> • FQDN de la web externa  <br/> Y  <br/> • Dirección URL de acceso telefónico simple  <br/> • Cumplir con direcciones URL simples por dominio SIP  <br/> O BIEN  <br/> • Una entrada comodín para las direcciones URL simples  <br/> |SN=se01.contoso.com; SAN=webcon01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com  <br/> Con un certificado de comodín:  <br/> SN = SE01. contoso. com; SAN = webcon01. contoso. com; SAN =\*. contoso.com  <br/> |Si tiene varias direcciones URL simples, tiene que incluirlas como nombres alternativos de asunto.  <br/> Las entradas de comodín se admiten para las entradas de direcciones URL sencillas.  <br/> |
   
Certificados para servidores front-end en un grupo de servidores front-end:
  
|**Certificado**|**Nombre de sujeto/Nombre común**|**Nombre alternativo de sujeto**|**Ejemplo**|**Comentarios**|
|:-----|:-----|:-----|:-----|:-----|
|Predeterminado  <br/> |FQDN del grupo de servidores  <br/> |FQDN del grupo y FQDN del servidor  <br/> Si hay varios dominios SIP y está habilitada la configuración automática de los clientes, el Asistente para certificados detectará y agregará los FQDN de todos los dominios SIP admitidos.  <br/> Si este grupo de servidores es el servidor de inicio automático de sesión de los clientes y se requiere una correspondencia exacta del sistema de nombres de dominio (DNS) en la directiva del grupo, necesitará también entradas para sip.sipdomain (para cada uno de los dominios SIP que tenga).  <br/> |SN=eepool.contoso.com; SAN=eepool.contoso.com; SAN=ee01.contoso.com   <br/> Si este grupo de servidores es el servidor de inicio automático de sesión de los clientes y se requiere una correspondencia exacta de DNS en la directiva del grupo, necesitará también SAN=sip.contoso.com; SAN=sip.fabrikam.com  <br/> |El asistente detecta todos los dominios SIP especificados durante la instalación y los agrega automáticamente al nombre alternativo de sujeto.  <br/> También puede usar este certificado para la autenticación de servidor a servidor.  <br/> |
|Web interno  <br/> |FQDN del grupo de servidores  <br/> |Cada uno de los siguientes elementos:  <br/> • FQDN de la web interna (que no es el mismo que el FQDN del servidor)  <br/> • FQDN del servidor  <br/> • FQDN del grupo de Skype empresarial  <br/> Y  <br/> • Cumplir con direcciones URL simples  <br/> • Dirección URL de acceso telefónico simple  <br/> • Dirección URL simple de administración  <br/> O BIEN  <br/> • Una entrada comodín para las direcciones URL simples  <br/> |SN=ee01.contoso.com; SAN=ee01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com; SAN=admin.contoso.com  <br/> Con un certificado de comodín:  <br/> SN = ee01. contoso. com; SAN = ee01. contoso. com; SAN =\*. contoso.com  <br/> |Si tiene varias direcciones URL simples, tiene que incluirlas como nombres alternativos de asunto.  <br/> Las entradas de comodín se admiten para las entradas de direcciones URL sencillas.  <br/> |
|Web externo  <br/> |FQDN del grupo de servidores  <br/> |Cada uno de los siguientes elementos:  <br/> • FQDN de la web externa  <br/> Y  <br/> • Dirección URL de acceso telefónico simple  <br/> • Dirección URL simple de administración  <br/> O BIEN  <br/> • Una entrada comodín para las direcciones URL simples  <br/> |SN=ee01.contoso.com; SAN=webcon01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com  <br/> Con un certificado de comodín:  <br/> SN = ee01. contoso. com; SAN = webcon01. contoso. com; SAN =\*. contoso.com  <br/> |Si tiene varias direcciones URL simples, tiene que incluirlas como nombres alternativos de asunto.  <br/> Las entradas de comodín se admiten para las entradas de direcciones URL sencillas.  <br/> |
   
Certificados para el Director:
  
|**Certificado**|**Nombre de sujeto/Nombre común**|**Nombre alternativo de sujeto**|**Ejemplo**|
|:-----|:-----|:-----|:-----|
|Valor predeterminado  <br/> |Grupo de directores  <br/> |FQDN del Director, FQDN del grupo de directores.  <br/> Si este grupo es el servidor de inicio de sesión automático para clientes y se requiere coincidencia de DNS estricta en la Directiva de grupo, también necesitará entradas para SIP. sipdomain (para cada dominio SIP que tenga).  <br/> |pool.contoso.com; SAN=dir01.contoso.com   <br/> Si este grupo de directores es el servidor de inicio de sesión automático para clientes y se requiere una coincidencia de DNS estricta en la Directiva de grupo, también necesita SAN = SIP. contoso. com; SAN = SIP. fabrikam. com  <br/> |
|Web interno  <br/> |FQDN del servidor  <br/> |Cada uno de los siguientes elementos:  <br/> • FQDN de la web interna (que es el mismo que el FQDN del servidor)  <br/> • FQDN del servidor  <br/> • FQDN del grupo de Skype empresarial  <br/> Y  <br/> • Cumplir con direcciones URL simples  <br/> • Dirección URL de acceso telefónico simple  <br/> • Dirección URL simple de administración  <br/> O BIEN  <br/> • Una entrada comodín para las direcciones URL simples  <br/> |SN=dir01.contoso.com; SAN=dir01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com; SAN=admin.contoso.com  <br/> Con un certificado de comodín:  <br/> SN = dir01. contoso. com; SAN = dir01. contoso. com SAN =\*. contoso.com  <br/> |
|Web externo  <br/> |FQDN del servidor  <br/> |Cada uno de los siguientes elementos:  <br/> • FQDN de la web externa  <br/> Y  <br/> • Cumplir con direcciones URL simples por dominio SIP  <br/> • Dirección URL de acceso telefónico simple  <br/> O BIEN  <br/> • Una entrada comodín para las direcciones URL simples  <br/> |El FQDN de la web externa del Director debe ser diferente del de la aplicación front end o del servidor front-end.  <br/> SN=dir01.contoso.com; SAN=directorwebcon01.contoso.com SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com  <br/> Con un certificado de comodín:  <br/> SN = dir01. contoso. com; SAN = directorwebcon01. contoso. com SAN =\*. contoso.com  <br/> |
   
Certificados para el servidor de mediación independiente:
  
|**Certificado**|**Nombre de sujeto/Nombre común**|**Nombre alternativo de sujeto**|**Ejemplo**|
|:-----|:-----|:-----|:-----|
|Valor predeterminado  <br/> |FQDN del grupo de servidores  <br/> |FQDN del grupo de servidores  <br/> FQDN del miembro del grupo de servidores  <br/> |SN=medsvr-pool.contoso.net; SAN=medsvr-pool.contoso.net; SAN=medsvr01.contoso.net  <br/> |
   
Certificados para dispositivos de rama supervivientes:
  
|**Certificado**|**Nombre de sujeto/Nombre común**|**Nombre alternativo de sujeto**|**Ejemplo**|
|:-----|:-----|:-----|:-----|
|Predeterminado  <br/> |FQDN de la aplicación  <br/> |SIP. \<sipdomain\> (solo necesita una entrada por dominio SIP)  <br/> |SN=sba01.contoso.net; SAN=sip.contoso.com; SAN=sip.fabrikam.com  <br/> |
   
### <a name="certificates-for-your-persistent-chat-server"></a>Certificados para el servidor de chat persistente

Al instalar el servidor de chat persistente, necesitará un certificado emitido por la misma CA que el usado por sus servidores internos de Skype empresarial Server 2015. Debe hacerse para cada servidor que ejecute los servicios Web de chat persistente para la carga y descarga de archivos. Le recomendamos enfáticamente que tenga los certificados necesarios antes de iniciar la instalación de chat persistente, y si su CA es externa, aún más (esto puede tardar un poco de tiempo en emitirse).
  
### <a name="certificates-for-external-user-access-edge"></a>Certificados para el acceso de usuarios externos (Edge)

Skype empresarial Server 2015 admite el uso de un **único certificado público** para las interfaces externas de acceso y de conferencia Web, además del servicio de autenticación a/V, que se proporciona a través de los servidores perimetrales. Normalmente, tu interfaz interna de Edge usará un certificado privado emitido por tu entidad de certificación interna, pero si lo prefieres, también puedes usar un certificado público para esto, si procede de una entidad de certificación de confianza.
  
Su proxy inverso (RP) también usa un certificado público y cifra sus propias comunicaciones con los clientes y los servidores internos mediante HTTP (o, para ser más precisos, TLS por HTTP).
  
### <a name="certificates-for-mobility"></a>Certificados para movilidad

Si va a implementar la movilidad y está admitido el descubrimiento automático para clientes móviles, tendrá que incluir entradas de nombre alternativo de asunto adicionales en sus certificados para admitir las conexiones seguras de los clientes móviles.
  
¿Qué certificados? Necesitará nombres SAN para el descubrimiento automático en los certificados aquí:
  
- Grupo de directores
    
- Grupo de servidores front-end
    
- Proxy inverso
    
En las siguientes tablas se ofrecen detalles.
  
Ahora, aquí es donde un poco de preplanificación es bueno, pero a veces ha implementado Skype empresarial Server 2015 sin tener que implementar movilidad, y esto se enciende cuando ya tiene certificados en su entorno. Volver a emitir los certificados desde una CA interna suele ser sencillo, pero en el caso de una CA pública puede resultar un poco más caro.
  
Si eso es lo que busca y tiene una gran cantidad de dominios SIP (lo que dificultaría la adición de las San), puede configurar su proxy inverso para usar HTTP en la solicitud de servicio de detección automática inicial, en lugar de usar HTTPS (que es el valor predeterminado configuración). Tiene más información en el tema Planificación para la movilidad.
  
Requisitos del certificado de grupo de directores y grupo de servidores front-end:
  
|**Descripción**|**Entrada SAN**|
|:-----|:-----|
|URL del servicio Detección automática interna  <br/> |SAN = lyncdiscoverinternal. \<sipdomain\>  <br/> |
|URL del servicio Detección automática externa  <br/> |SAN = lyncdiscover. \<sipdomain\>  <br/> |
   
También puede usar SAN =\*. \<sipdomain\>
  
Requisitos de certificado (CA pública) de proxy inverso
  
|**Descripción**|**Entrada SAN**|
|:-----|:-----|
|URL del servicio Detección automática externa  <br/> |SAN = lyncdiscover. \<sipdomain\>  <br/> |
   
Este SAN debe asignarse al certificado asignado al agente de escucha SSL de su proxy inverso.
  
> [!NOTE]
> Su agente de escucha de proxy inverso va a tener redes SAN para las URL de los servicios web externos. Algunos ejemplos serían SAN = skypewebextpool01. contoso. com y dirwebexternal.contoso.com, si ha implementado el director, (que es opcional). 
  
## <a name="file-share"></a>Recurso compartido de archivos
<a name="Fileshare"> </a>

Skype empresarial Server 2015 puede usar el mismo recurso compartido de archivos para todo el almacenamiento de archivos. Deberá tener en cuenta lo siguiente:
  
- Un recurso compartido de archivos debe estar en un almacenamiento conectado directo (DAS) o en un almacenamiento en red (SAN), y esto incluye el sistema de archivos distribuidos (DFS) y las matrices redundantes de discos independientes (RAID). Para obtener más información sobre DFS para Windows Server 2012, consulte [esta página de DFS](https://technet.microsoft.com/library/jj127250.aspx).
    
- Recomendamos un clúster compartido para el recurso compartido de archivos. Si está usando una, debería crear un clúster de Windows Server 2012 o Windows Server 2012 R2. Windows Server 2008 R2 también es aceptable. ¿Por qué es la última versión de Windows? Es posible que las versiones anteriores no tengan los permisos adecuados para habilitar todas las características. Puede usar el administrador de clústeres para crear los recursos compartidos de archivos, y este [procedimiento para crear recursos compartidos de archivos en un clúster](https://support.microsoft.com/en-us/help/224967/how-to-create-file-shares-on-a-cluster) le ayudará con esos detalles.
    
> [!CAUTION] 
> Es preciso que recuerde que no se admite el uso del almacenamiento conectado a la red (NAS) como recurso compartido de archivo, de modo que utilice una de las opciones que se han descrito anteriormente. 
  

