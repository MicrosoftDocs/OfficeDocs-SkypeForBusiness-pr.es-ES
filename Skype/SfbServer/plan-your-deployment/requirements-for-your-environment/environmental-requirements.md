---
title: Requisitos del entorno Skype Empresarial Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/15/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 4812c444-2546-48d7-9ca7-b71fce508ed8
description: 'Resumen: configure los requisitos que no son del servidor para Skype Empresarial Server 2015. Hay una variedad de cosas que querrá configurar antes de realizar la implementación, incluidos Active Directory, DNS, Certs y Fileshares.'
ms.openlocfilehash: e27d854b2755a3d0d8613f12fb80342879faab26
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/30/2021
ms.locfileid: "58725959"
---
# <a name="environmental-requirements-for-skype-for-business-server-2015"></a>Requisitos del entorno Skype Empresarial Server 2015
 
**Resumen:** Configure los requisitos que no son del servidor para Skype Empresarial Server 2015. Hay una variedad de cosas que querrá configurar antes de realizar la implementación, incluidos Active Directory, DNS, Certs y Fileshares.
  
¿Cuál es un requisito ambiental para Skype Empresarial Server 2015? Bueno, hemos puesto todo lo que no está directamente relacionado con el servidor en este tema, por lo que no tiene que hacer tanto clic alrededor. Si está buscando requisitos previos del servidor, puede consultar el documento Requisitos del [](../../plan-your-deployment/network-requirements/network-requirements.md) servidor [para Skype Empresarial Server 2015.](server-requirements.md) La planeación de redes también se documenta por separado. De lo contrario, esto es lo que tenemos en este artículo:
  
- [Active Directory](environmental-requirements.md#AD)
  
- [Sistema de nombres de dominio (DNS)](environmental-requirements.md#DNS)
  
- [Certificados](environmental-requirements.md#Certs)
  
- [Recurso compartido de archivos](environmental-requirements.md#Fileshare)
  
## <a name="active-directory"></a>Active Directory
<a name="AD"> </a>

Aunque muchos datos de configuración para servidores y servicios se almacenan en el almacén de administración central de Skype Empresarial Server 2015, todavía hay algunas cosas almacenadas en Active Directory:
  
|**Objetos de Active Directory**|**Tipos de objeto**|
|:-----|:-----|
|Extensiones de esquema  <br/> |Extensiones de objetos de usuario  <br/> |
||Extensiones para Lync Server 2013 y Lync Server 2010, para mantener la compatibilidad con versiones anteriores admitidas.  <br/> |
|Datos  <br/> |URI de SIP del usuario y otros parámetros de usuario  <br/> |
||Objetos de contacto para aplicaciones (como la aplicación grupo de respuesta y el aplicación Operador de conferencia).  <br/> |
||Datos publicados por compatibilidad con versiones anteriores.  <br/> |
||Un punto de control de servicio (SCP) para el almacén de administración central.  <br/> |
||Cuenta de autenticación Kerberos (un objeto de equipo opcional).  <br/> |
   
### <a name="os-for-domain-controllers"></a>Sistema operativo para controladores de dominio

Por lo tanto, ¿qué sistema operativo de controlador de dominio se puede usar? Tenemos la siguiente lista:

- Windows Server 2019 (debe tener Skype Empresarial Server 2015 Cumulative Update 5 o posterior)
  
- Windows Server 2016
    
- Windows Server 2012 R2
    
- Windows Server 2012
    
- Windows Server 2008 R2
    
- Windows Server 2008
    
Ahora, el nivel funcional de dominio de cualquier dominio en el que implemente Skype Empresarial Server 2015 y el nivel funcional del bosque de cualquier bosque en el que implemente Skype Empresarial Server 2015, debe ser uno de los siguientes:

- Windows Server 2019 (debe tener Skype Empresarial Server 2015 Cumulative Update 5 o posterior)
  
- Windows Server 2016
    
- Windows Server 2012 R2
    
- Windows Server 2012
    
- Windows Server 2008 R2
    
- Windows Server 2008
    
- Windows Server 2003
    
¿Puede tener controladores de dominio de solo lectura en estos entornos? Seguro, siempre y cuando también haya controladores de dominio grabables disponibles en el mismo sitio que el Skype Empresarial Server.
  
Ahora, es importante saber que Skype Empresarial Server 2015 no admite dominios con etiqueta única. ¿Cuáles son? Si tiene un dominio raíz etiquetado como contoso.local, estará bien. Si tiene un dominio raíz que se acaba de llamar local, no funcionará y no se admite como resultado. Un poco más sobre esto se ha escrito [en este artículo de Knowledge Base](https://support.microsoft.com/kb/300684/en-us).
  
Skype Empresarial Server 2015 tampoco admite el cambio de nombre de dominios. If you've really got to do that, then you'll need to uninstall Skype Empresarial Server 2015, do the domain rename, and then reinstall Skype Empresarial Server 2015.
  
Por último, es posible que esté tratando con un dominio con un entorno de AD DS bloqueado y eso está bien. Tenemos más información sobre cómo implementar Skype Empresarial Server 2015 en ese tipo de entorno en los documentos de implementación.
  
### <a name="ad-topologies"></a>Topologías de AD

Skype Empresarial Server las topologías admitidas de 2015 son:
  
- Un solo bosque con un solo dominio
    
- Un solo bosque con un solo árbol y varios dominios
    
- Un solo bosque con varios árboles y espacios de nombres separados
    
- Varios bosques en una topología de bosque central
    
- Varios bosques en una topología de bosque de recursos
    
- Varios bosques en una topología Skype Empresarial bosque de recursos con Exchange Online
    
- Varios bosques en una topología de bosque de recursos con Skype Empresarial Online y Azure Active Directory Conectar
    
Tenemos diagramas y descripciones para ayudarle a determinar qué topología tiene en su entorno o qué puede necesitar configurar antes de instalar Skype Empresarial Server 2015. Para que sea sencillo, también estamos incluyendo una clave:
  
![Es una clave de los iconos usados para Skype Empresarial diagramas de topología.](../../media/cc0dbc17-cf81-4b79-bf99-4614cc6828a0.png)
  
#### <a name="single-forest-with-single-domain"></a>Un solo bosque con un solo dominio

![Diagrama de bosque único de Active Directory con un solo dominio.](../../media/24921a0b-3a3e-4bad-8427-49300e2e3f7a.png)
  
No es más fácil que esto, es un bosque de dominio único, es una topología común.
  
#### <a name="single-forest-with-a-single-tree-and-multiple-domains"></a>Un solo bosque con un solo árbol y varios dominios

![Un solo bosque, un solo árbol y un diagrama de dominios mutiple.](../../media/63b9f0dd-6bac-4ba9-ae68-8be032d09dcb.png)
  
Este diagrama muestra un solo bosque, de nuevo, pero también tiene uno o varios dominios secundarios (hay tres en este ejemplo específico). Por lo tanto, el dominio en el que se crean los usuarios puede ser diferente del dominio Skype Empresarial Server se implementa 2015. ¿Por qué preocuparse por esto? Es importante recordar que al implementar un grupo Skype Empresarial Server front-end, todos los servidores de ese grupo deben estar en un solo dominio. Puede tener administración entre dominios a través de Skype Empresarial Server la compatibilidad de Windows grupos de administrador universales.
  
De vuelta al diagrama anterior, puede ver que los usuarios de un dominio pueden tener acceso Skype Empresarial Server grupos de servidores desde el mismo dominio o desde dominios diferentes, incluso si esos usuarios están en un dominio secundario.
  
#### <a name="single-forest-with-multiple-trees-and-disjoint-namespaces"></a>Un solo bosque con varios árboles y espacios de nombres separados

![Un solo bosque, varios árboles y un diagrama de espacios de nombres distintos.](../../media/5ede77a1-f5d2-499c-a2c8-d02f3c2f7cd7.png)
  
Puede ser que tenga una topología similar a este diagrama, donde tiene un bosque, pero dentro de ese bosque hay varios dominios, con espacios de nombres de AD independientes. Si ese es el caso, este diagrama es una buena ilustración, ya que tenemos usuarios en tres dominios diferentes que tienen acceso a Skype Empresarial Server 2015. Las líneas sólidas indican que tienen acceso a un grupo de Skype Empresarial Server en su propio dominio, mientras que una línea discontinua indica que van a un grupo de servidores en un árbol diferente por completo.
  
Como puede ver, los usuarios del mismo dominio, el mismo árbol o incluso un árbol diferente pueden tener acceso a los grupos de servidores correctamente.
  
#### <a name="multiple-forests-in-a-central-forest-topology"></a>Varios bosques en una topología de bosque central

![Varios bosques en un diagrama de topología de bosque central.](../../media/fec40746-4254-4c84-86b9-aad4a616ea2f.png)
  
Skype Empresarial Server 2015 admite varios bosques configurados en una topología de bosque central. Si no está seguro de que eso es lo que tiene, el bosque central de la topología usa objetos en él para representar a los usuarios de los demás bosques y hospeda cuentas de usuario para los usuarios del bosque.
  
¿Cómo funciona esto? Bueno, un producto de sincronización de directorios (como Forefront Identity Manager o FIM) administra las cuentas de usuario de la organización a lo largo de su existencia. Cuando se crea o elimina una cuenta de un bosque, ese cambio se sincroniza con el contacto correspondiente en el bosque central.
  
Claramente, si la infraestructura de AD se está moviendo a esta topología podría no ser fácil, pero si ya está allí o aún planea la infraestructura del bosque, esta puede ser una buena opción. Puede centralizar la implementación Skype Empresarial Server 2015 en un solo bosque, mientras que los usuarios pueden buscar, comunicarse y ver la presencia de otros usuarios en cualquier bosque. Todas las actualizaciones de contacto de usuario se controlan automáticamente con software de sincronización.
  
#### <a name="multiple-forests-in-a-skype-for-business-resource-forest-topology"></a>Varios bosques en una topología Skype Empresarial bosque de recursos
<a name="BKMK_multipleforestopology"> </a>

![Varios bosques en un diagrama de topología de bosque de recursos.](../../media/41efa3b6-d9e6-47df-992b-fefcfc39a80d.png)
  
También se admite una topología de bosque de recursos; es donde un bosque está dedicado a ejecutar las aplicaciones de servidor, como Microsoft Exchange Server y Skype Empresarial Server 2015. Este bosque de recursos también hospeda una representación sincronizada de objetos de usuario activos, pero no cuentas de usuario habilitadas para inicio de sesión. Por lo tanto, el bosque de recursos es un entorno de servicios compartidos para otros bosques en los que residen objetos de usuario y tienen una relación de confianza de nivel de bosque con el bosque de recursos.
  
Tenga en cuenta que Exchange Server puede implementarse en el mismo bosque de recursos que Skype Empresarial Server o en un bosque diferente.
  
Para implementar Skype Empresarial Server 2015 en este tipo de topología, crearía un objeto de usuario deshabilitado en el bosque de recursos para cada cuenta de usuario de los bosques de usuarios (si Microsoft Exchange Server ya está en el entorno, esto podría hacerse por usted). A continuación, necesitará una herramienta de sincronización de directorios (como Forefront Identity Manager o FIM) para administrar cuentas de usuario durante su ciclo de vida.
  
#### <a name="multiple-forests-in-a-skype-for-business-resource-forest-topology-with-exchange-online"></a>Varios bosques en una topología Skype Empresarial bosque de recursos con Exchange Online
<a name="BKMK_multipleforestopology"> </a>

Esta topología es similar a la topología descrita en [Multiple forests in a Skype Empresarial resource forest topology](environmental-requirements.md#BKMK_multipleforestopology).
  
En esta topología, hay uno o más bosques de usuarios y Skype Empresarial Server se implementa en un bosque de recursos dedicado. Exchange Server puede implementarse localmente en el mismo bosque de recursos o en un bosque diferente y configurarse para servicios híbridos con Exchange Online, o los servicios de correo electrónico pueden ser proporcionados exclusivamente por Exchange Online para las cuentas locales. No hay ningún diagrama disponible para esta topología.
  
#### <a name="multiple-forests-in-a-resource-forest-topology-with-skype-for-business-online-and-azure-active-directory-connect"></a>Varios bosques en una topología de bosque de recursos con Skype Empresarial Online y Azure Active Directory Conectar
<a name="BKMK_multipleforestopology"> </a>

![Muestra dos bosques de AD, un bosque de usuarios y un bosque de recursos. Los dos bosques tienen una relación de confianza. Se sincronizan con Microsoft 365 o Office 365 con Azure AD Conectar. Todos los usuarios están habilitados para Skype Empresarial mediante Microsoft 365 o Office 365.](../../media/6d54558d-8786-4ebf-90f6-55ae3fdb5ae7.jpg)
  
Con este escenario, hay varios bosques locales, con una topología de bosque de recursos. Existe una relación de plena confianza entre los bosques de Active Directory. La Azure Active Directory Conectar se usa para sincronizar cuentas entre los bosques de usuarios locales y Microsoft 365 o Office 365.
  
 La organización también tiene Microsoft 365 o Office 365 y [](/previous-versions/azure/azure-services/dn832695(v=azure.100)) usa Azure Active Directory Conectar para sincronizar sus cuentas locales con Microsoft 365 o Office 365. Los usuarios que están habilitados para Skype Empresarial están habilitados mediante Microsoft 365 o Office 365 y Skype Empresarial Online. Skype Empresarial Server no se implementa localmente.
  
La autenticación de inicio de sesión único la proporciona una granja de servicios de federación de Active Directory ubicada en el bosque de usuarios.
  
En este escenario, se admite implementar Exchange local, Exchange Online, una solución de Exchange híbrida o no tener Exchange implementado en absoluto. (El diagrama solo muestra Exchange local, pero las otras Exchange también son totalmente compatibles).
  
#### <a name="multiple-forests-in-a-resource-forest-topology-with-hybrid-skype-for-business"></a>Varios bosques en una topología de bosque de recursos con Skype Empresarial
<a name="BKMK_multipleforestopology"> </a>

En este escenario, hay uno o varios bosques de usuarios locales y Skype Empresarial se implementa en un bosque de recursos dedicado y se configura para el modo híbrido con Skype Empresarial Online. Exchange Server puede implementarse localmente en el mismo bosque de recursos o en un bosque diferente y puede configurarse para híbrido con Exchange Online. Como alternativa, los servicios de correo electrónico pueden ser proporcionados exclusivamente por Exchange Online para las cuentas locales.
  
Para obtener más información, vea [Configure a multi-forest environment for hybrid Skype Empresarial](../../../SfbHybrid/hybrid/configure-a-multi-forest-environment-for-hybrid.md?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json).
  
## <a name="domain-name-system-dns"></a>Sistema de nombres de dominio (DNS)
<a name="DNS"> </a>

Skype Empresarial Server 2015 requiere DNS, por los siguientes motivos:
  
- DNS permite Skype Empresarial Server 2015 detectar servidores o grupos de servidores internos, lo que permite comunicaciones de servidor a servidor.
    
- DNS permite a los equipos cliente detectar el grupo de servidores front-end o Standard Edition servidor que se usa para transacciones SIP.
    
- Asocia direcciones URL sencillas para conferencias con los servidores que hospedan dichas conferencias.
    
- DNS permite que los usuarios externos y los equipos cliente se conecten a los servidores perimetrales, o al proxy inverso HTTP, para mensajería instantánea (MI) o conferencias.
    
- Permite a los dispositivos de comunicaciones unificadas (UC) que no han iniciado sesión descubrir el grupo de servidores front-end o el servidor Standard Edition que ejecuta el servicio web de actualización de dispositivos para obtener actualizaciones y enviar registros.
    
- El uso de DNS permite a los clientes móviles detectar automáticamente recursos de servicios web sin necesidad de que los usuarios escriban manualmente direcciones URL en la configuración del dispositivo.
    
- Y se usa en el equilibrio de carga DNS.
    
Es importante tener en cuenta que Skype Empresarial Server 2015 no admite nombres de dominio internacionalizados (IDN).
  
Y es extremadamente importante recordar que cualquier nombre de DNS es idéntico al nombre del equipo configurado en cualquier servidor que Skype Empresarial Server 2015. En concreto, no podemos tener nombres cortos en el entorno y debemos tener FQDN para el Generador de topologías.
  
Esto parece lógico para cualquier equipo que ya esté unido a un dominio, pero si tiene un servidor perimetral que no está unido a su dominio, puede tener un nombre corto predeterminado, sin sufijo de dominio. Asegúrese de que ese no sea el caso, ya sea en DNS o en el servidor perimetral, o en cualquier servidor o grupo de servidores de 2015 de Skype Empresarial Server 2015, en ese caso.
  
Y definitivamente no use caracteres Unicode ni guiones bajos. Los caracteres estándar (que son A-Z, a-z, 0-9 y guiones) son los que van a ser compatibles con DNS externos y autoridades de certificados públicas (deberá asignar FQDN al SN en el certificado, no olvide), por lo que se ahorrará mucho dolor si se asigna un nombre con esto en mente.
  
Para obtener más información sobre los requisitos dns para redes, consulte la [sección Redes](../../plan-your-deployment/network-requirements/network-requirements.md) de nuestra documentación de planeación.
  
## <a name="certificates"></a>Certificados
<a name="Certs"> </a>

Una de las cosas más importantes que puede hacer antes de implementar es asegurarse de que tiene los certificados en orden. Skype Empresarial Server 2015 necesita una infraestructura de clave pública (PKI) para la seguridad de la capa de transporte (TLS) y las conexiones de seguridad de la capa de transporte mutua (MTLS). Básicamente, para comunicarse de forma segura de forma estandarizada, Skype Empresarial Server certificados emitidos por las autoridades de certificación (CA).
  
Estas son algunas de las cosas que Skype Empresarial Server 2015 usa certificados para:
  
- Conexiones TLS entre clientes y servidores
    
- Conexiones MTLS entre servidores
    
- Federación mediante la detección automática basada en DNS de los socios
    
- Acceso de usuarios remotos a la mensajería instantánea (IM)
    
- Acceso de usuarios externos a sesiones de audio y vídeo (AV), uso compartido de aplicaciones y conferencias
    
- Hablar con aplicaciones web y Outlook Web Access (OWA)
    
Por lo tanto, la planeación de certificados es imprescindible. Ahora, veamos una lista de algunas de las cosas que debe tener en cuenta al solicitar certificados:
  
- Todos los certificados de servidor deben admitir la autorización de servidor (EKU de servidor).
    
- Todos los certificados de servidor deben contener un punto de distribución CRL (CDP).
    
- Todos los certificados deben firmarse con un algoritmo de firma admitido por el sistema operativo. Skype Empresarial Server 2015 admite el conjunto de tamaños de síntesis SHA-1 y SHA-2 (224, 256, 384 y 512 bits) y cumple o supera los requisitos del sistema operativo.
    
- La inscripción automática es compatible con servidores internos que ejecutan Skype Empresarial Server 2015.
    
- La inscripción automática no se admite Skype Empresarial Server servidores perimetrales de 2015.
    
- Cuando envíe una solicitud de certificado web a una entidad de certificación de Windows Server 2003, deberá hacerlo desde un equipo que ejecute Windows Server 2003 con SP2 o Windows XP.
    
> [!NOTE]
> Aunque KB922706 proporciona compatibilidad para resolver problemas con la inscripción de certificados web en una inscripción web de servicios de certificados de Windows Server 2003, no permite usar Windows Server 2008, Windows Vista o Windows 7 para solicitar un certificado de una CA de Windows Server 2003. 
  
> [!NOTE]
> El uso del algoritmo de firma RSASSA-PSS no es compatible y puede provocar errores en el inicio de sesión y el reenvío de llamadas, entre otros problemas. 

> [!NOTE]
> Skype Empresarial Server 2015 no admite certificados de CNG.
  
- Se admiten longitudes de clave de cifrado de 1024, 2048 y 4096. Se recomiendan longitudes clave de 2048 y superiores.
    
- El algoritmo predeterminado de síntesis o firma hash es RSA. También ECDH_P256, ECDH_P384 y ECDH_P521 algoritmos.
    
Por lo tanto, eso es mucho que pensar y, definitivamente, hay una variedad de niveles de comodidad con la solicitud de certificados de una CA. Le proporcionaremos más información a continuación para que su planeación sea lo más indolor posible.
  
### <a name="certificates-for-your-internal-servers"></a>Certificados para los servidores internos

Necesitará certificados para la mayoría de los servidores internos y lo más probable es que los obtenga de una CA interna (es decir, uno ubicado en su dominio). Si lo desea, puede solicitar estos certificados a una CA externa (una ubicada en Internet). Si se pregunta a qué entidad de certificación pública [](../../../SfbPartnerCertification/certification/services-ssl.md) debe ir, consulte la lista de asociados de certificados de comunicaciones unificadas.
  
También necesitará certificados cuando Skype Empresarial Server 2015 se comunique con otras aplicaciones y servidores, como Microsoft Exchange Server. Obviamente, esto tendrá que ser un certificado que estas otras aplicaciones y servidores puedan usar de forma compatible. Skype Empresarial Server 2015 y otros productos de Microsoft admiten el protocolo de autorización abierta (OAuth) para la autenticación y autorización de servidor a servidor. Si está interesado en esto, tenemos un artículo de planeación adicional para OAuth y Skype Empresarial Server 2015.
  
Skype Empresarial Server 2015 también incluye compatibilidad con certificados firmados (sin necesidad de) mediante la función hash criptográfica SHA-256. Para admitir el acceso externo con SHA-256, una CA pública debe emitir el certificado externo mediante SHA-256.
  
Para intentar que las cosas sean sencillas, hemos incluido los requisitos de certificado para servidores Standard Edition, grupos de servidores front-end y otros roles en las tablas siguientes, con el contoso.com ficticio que se usa para ejemplos (probablemente usará otra cosa para su entorno). Todos estos son certificados de servidor web estándar, con claves privadas que no son exportables. Algunas cosas adicionales que debe tener en cuenta:
  
- El uso de clave mejorado (EKU) del servidor se configura automáticamente cuando se usa el asistente para certificados para solicitar certificados.
    
- Cada nombre descriptivo del certificado debe ser único en el almacén del equipo.
    
- Según los nombres de ejemplo siguientes, si ha configurado sipinternal.contoso.com o sipexternal.contoso.com en su DNS, deben agregarse al nombre alternativo de sujeto (SAN) del certificado.
    
Certificados para servidores Standard Edition:
  
|**Certificado**|**Nombre del sujeto/Nombre común**|**Nombre alternativo de sujeto**|**Ejemplo**|**Comments**|
|:-----|:-----|:-----|:-----|:-----|
|Predeterminado  <br/> |FQDN del grupo de servidores  <br/> |FQDN del grupo de servidores y FQDN del servidor  <br/> Si hay varios dominios SIP y está habilitada la configuración automática de los clientes, el Asistente para certificados detectará y agregará los FQDN de todos los dominios SIP admitidos.  <br/> Si este grupo de servidores es el servidor de inicio automático de sesión de los clientes y se requiere una correspondencia exacta del sistema de nombres de dominio (DNS) en la directiva del grupo, necesitará también entradas para sip.sipdomain (para cada uno de los dominios SIP que tenga).  <br/> |SN=se01.contoso.com; SAN=se01.contoso.com  <br/> Si este grupo de servidores es el servidor de inicio automático de sesión de los clientes y se necesita una correspondencia exacta de DNS en la directiva del grupo, necesitará también SAN=sip.contoso.com; SAN=sip.fabrikam.com  <br/> |En el servidor Standard Edition, el FQDN del servidor es igual que el FQDN del grupo de servidores.  <br/> El asistente detecta los dominios SIP que especificó durante la instalación y los agrega automáticamente como nombres alternativos de sujeto.  <br/> También puede usar este certificado para la autenticación de servidor a servidor.  <br/> |
|Web interno  <br/> |FQDN del servidor  <br/> |Cada uno de los siguientes elementos:  <br/> • FQDN web interno (que es el mismo que el FQDN del servidor)  <br/> AND  <br/> • Reunirse con direcciones URL sencillas  <br/> • Dirección URL sencilla de acceso telefónico  <br/> • Dirección URL sencilla de administración  <br/> OR  <br/> • Una entrada comodín para las direcciones URL sencillas  <br/> |SN=se01.contoso.com; SAN=se01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com; SAN=admin.contoso.com  <br/> Con un certificado de comodín:  <br/> SN=se01.contoso.com; SAN=se01.contoso.com; SAN= \* .contoso.com  <br/> |No puede invalidar el FQDN web interno en el Generador de topologías.  <br/> Si tiene varias direcciones URL sencillas de Meet, debe incluirlas todas como SAN.  <br/> Las entradas de comodín se admiten para las entradas de direcciones URL sencillas.  <br/> |
|Web externo  <br/> |FQDN del servidor  <br/> |Cada uno de los siguientes elementos:  <br/> • FQDN web externo  <br/> AND  <br/> • Dirección URL sencilla de acceso telefónico  <br/> • Reunirse con direcciones URL sencillas por dominio SIP  <br/> OR  <br/> • Una entrada comodín para las direcciones URL sencillas  <br/> |SN=se01.contoso.com; SAN=webcon01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com  <br/> Con un certificado de comodín:  <br/> SN=se01.contoso.com; SAN=webcon01.contoso.com; SAN= \* .contoso.com  <br/> |Si tiene varias direcciones URL sencillas de Meet, debe incluirlas todas como nombres alternativos de sujeto.  <br/> Las entradas de comodín se admiten para las entradas de direcciones URL sencillas.  <br/> |
   
Certificados para servidores front-end en un grupo Enterprise Edition front-end:
  
|**Certificado**|**Nombre del sujeto/Nombre común**|**Nombre alternativo de sujeto**|**Ejemplo**|**Comments**|
|:-----|:-----|:-----|:-----|:-----|
|Predeterminado  <br/> |FQDN del grupo de servidores  <br/> |FQDN del grupo de servidores y FQDN del servidor  <br/> Si hay varios dominios SIP y está habilitada la configuración automática de los clientes, el Asistente para certificados detectará y agregará los FQDN de todos los dominios SIP admitidos.  <br/> Si este grupo de servidores es el servidor de inicio automático de sesión de los clientes y se requiere una correspondencia exacta del sistema de nombres de dominio (DNS) en la directiva del grupo, necesitará también entradas para sip.sipdomain (para cada uno de los dominios SIP que tenga).  <br/> |SN=eepool.contoso.com; SAN=eepool.contoso.com; SAN=ee01.contoso.com  <br/> Si este grupo de servidores es el servidor de inicio automático de sesión de los clientes y se necesita una correspondencia exacta de DNS en la directiva del grupo, necesitará también SAN=sip.contoso.com; SAN=sip.fabrikam.com  <br/> |El asistente detecta todos los dominios SIP especificados durante la instalación y los agrega automáticamente al nombre alternativo de sujeto.  <br/> También puede usar este certificado para la autenticación de servidor a servidor.  <br/> |
|Web interno  <br/> |FQDN del grupo de servidores  <br/> |Cada uno de los siguientes elementos:  <br/> • FQDN web interno (que NO es el mismo que el FQDN del servidor)  <br/> • FQDN de servidor  <br/> • Skype Empresarial FQDN del grupo de servidores  <br/> AND  <br/> • Reunirse con direcciones URL sencillas  <br/> • Dirección URL sencilla de acceso telefónico  <br/> • Dirección URL sencilla de administración  <br/> OR  <br/> • Una entrada comodín para las direcciones URL sencillas  <br/> |SN=ee01.contoso.com; SAN=ee01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com; SAN=admin.contoso.com  <br/> Con un certificado de comodín:  <br/> SN=ee01.contoso.com; SAN=ee01.contoso.com; SAN= \* .contoso.com  <br/> |Si tiene varias direcciones URL sencillas de Meet, debe incluirlas todas como nombres alternativos de sujeto.  <br/> Las entradas de comodín se admiten para las entradas de direcciones URL sencillas.  <br/> |
|Web externo  <br/> |FQDN del grupo de servidores  <br/> |Cada uno de los siguientes elementos:  <br/> • FQDN web externo  <br/> AND  <br/> • Dirección URL sencilla de acceso telefónico  <br/> • Dirección URL sencilla de administración  <br/> OR  <br/> • Una entrada comodín para las direcciones URL sencillas  <br/> |SN=ee01.contoso.com; SAN=webcon01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com  <br/> Con un certificado de comodín:  <br/> SN=ee01.contoso.com; SAN=webcon01.contoso.com; SAN= \* .contoso.com  <br/> |Si tiene varias direcciones URL sencillas de Meet, debe incluirlas todas como nombres alternativos de sujeto.  <br/> Las entradas de comodín se admiten para las entradas de direcciones URL sencillas.  <br/> |
   
Certificados para el director:
  
|**Certificado**|**Nombre del sujeto/Nombre común**|**Nombre alternativo de sujeto**|**Ejemplo**|
|:-----|:-----|:-----|:-----|
|Predeterminado  <br/> |Grupo de servidores Director  <br/> |FQDN del director, FQDN del grupo de directores.  <br/> Si este grupo es el servidor de inicio de sesión automático para clientes y se requiere una coincidencia de DNS estricta en la directiva de grupo, también necesitará entradas para sip.sipdomain (para cada dominio SIP que tenga).  <br/> |pool.contoso.com; SAN=dir01.contoso.com  <br/> Si este grupo de servidores del director es el servidor de inicio automático de sesión de los clientes y se necesita una correspondencia exacta de DNS en la directiva del grupo, necesitará también SAN=sip.contoso.com; SAN=sip.fabrikam.com  <br/> |
|Web interno  <br/> |FQDN del servidor  <br/> |Cada uno de los siguientes elementos:  <br/> • FQDN web interno (que es el mismo que el FQDN del servidor)  <br/> • FQDN de servidor  <br/> • Skype Empresarial FQDN del grupo de servidores  <br/> AND  <br/> • Reunirse con direcciones URL sencillas  <br/> • Dirección URL sencilla de acceso telefónico  <br/> • Dirección URL sencilla de administración  <br/> OR  <br/> • Una entrada comodín para las direcciones URL sencillas  <br/> |SN=dir01.contoso.com; SAN=dir01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com; SAN=admin.contoso.com  <br/> Con un certificado de comodín:  <br/> SN=dir01.contoso.com; SAN=dir01.contoso.com SAN= \* .contoso.com  <br/> |
|Web externo  <br/> |FQDN del servidor  <br/> |Cada uno de los siguientes elementos:  <br/> • FQDN web externo  <br/> AND  <br/> • Reunirse con direcciones URL sencillas por dominio SIP  <br/> • Dirección URL sencilla de acceso telefónico  <br/> OR  <br/> • Una entrada comodín para las direcciones URL sencillas  <br/> |El FQDN web externo de Director debe ser diferente del grupo de servidores front-end o el servidor front-end.  <br/> SN=dir01.contoso.com; SAN=directorwebcon01.contoso.com SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com  <br/> Con un certificado de comodín:  <br/> SN=dir01.contoso.com; SAN=directorwebcon01.contoso.com SAN= \* .contoso.com  <br/> |
   
Certificados para servidor de mediación independiente:
  
|**Certificado**|**Nombre del sujeto/Nombre común**|**Nombre alternativo de sujeto**|**Ejemplo**|
|:-----|:-----|:-----|:-----|
|Predeterminado  <br/> |FQDN del grupo de servidores  <br/> |FQDN del grupo de servidores  <br/> FQDN del servidor miembro del grupo  <br/> |SN=medsvr-pool.contoso.net; SAN=medsvr-pool.contoso.net; SAN=medsvr01.contoso.net  <br/> |
   
Certificados para la aplicación de sucursal con funciones de supervivencia:
  
|**Certificado**|**Nombre del sujeto/Nombre común**|**Nombre alternativo de sujeto**|**Ejemplo**|
|:-----|:-----|:-----|:-----|
|Predeterminado  <br/> |FQDN de la aplicación  <br/> |SIP.\<sipdomain\> (solo necesita una entrada por dominio SIP)  <br/> |SN=sba01.contoso.net; SAN=sip.contoso.com; SAN=sip.fabrikam.com  <br/> |
   
### <a name="certificates-for-your-persistent-chat-server"></a>Certificados para el servidor de chat persistente

Al instalar el servidor de chat persistente, necesitará un certificado emitido por la misma CA que el usado por los servidores internos de Skype Empresarial Server 2015. Esto debe hacerse para cada servidor que ejecute servicios web de chat persistente para archivos Upload/descarga. Le recomendamos encarecidamente que tenga los certificados necesarios antes de iniciar la instalación de chat persistente, y si su CA es externa, más aún (estas cosas pueden tardar un poco en emitirse).
  
### <a name="certificates-for-external-user-access-edge"></a>Certificados para el acceso de usuarios externos (Edge)

Skype Empresarial Server 2015 admite el uso de un único certificado público para interfaces externas perimetrales de acceso y conferencia web, además del servicio de autenticación A/V, que se proporciona **a** través de los servidores perimetrales. La interfaz interna perimetral normalmente usará un certificado privado emitido por la CA interna, pero si lo prefiere, también puede usar un certificado público para esto, si es de una CA de confianza.
  
El proxy inverso (RP) también va a usar un certificado público y cifra la comunicación de su RP a los clientes, y el RP a los servidores internos mediante HTTP (o más exactamente, TLS sobre HTTP).
  
### <a name="certificates-for-mobility"></a>Certificados para movilidad

Si va a implementar la movilidad y admite la detección automática para clientes móviles, tendrá que incluir algunas entradas de nombre alternativo de sujeto adicionales en los certificados para admitir las conexiones seguras de los clientes móviles.
  
¿Qué certificados? Necesitará nombres san para la detección automática en los certificados aquí:
  
- Grupo de servidores Director
    
- Grupo de servidores front-end
    
- Proxy inverso
    
Enumeraremos los detalles de cada tabla a continuación.
  
Ahora, aquí es donde un poco de planeación previa es buena, pero en ocasiones ha implementado Skype Empresarial Server 2015 sin tener la intención de implementar la movilidad, y eso se produce cuando ya tiene certificados en su entorno. La reedición a través de una CA interna suele ser bastante fácil, pero con certificados públicos de una CA pública, esto puede ser un poco más caro.
  
Si eso es lo que está viendo y si tiene muchos dominios SIP (lo que haría que agregar SANS sea más caro), puede configurar el proxy inverso para que use HTTP para la solicitud de servicio de detección automática inicial, en lugar de usar HTTPS (que es la configuración predeterminada). El tema Planning for Mobility tiene más información sobre esto.
  
Requisitos de certificado de grupo de directores y grupo de servidores front-end:
  
|**Descripción**|**Entrada san**|
|:-----|:-----|
|Dirección URL del servicio de detección automática interna  <br/> |SAN=lyncdiscoverinternal.\<sipdomain\>  <br/> |
|Dirección URL del servicio de detección automática externa  <br/> |SAN=lyncdiscover.\<sipdomain\>  <br/> |
   
También puede usar SAN= \* .\<sipdomain\>
  
Requisitos de certificado de proxy inverso (CA pública):
  
|**Descripción**|**Entrada san**|
|:-----|:-----|
|Dirección URL del servicio de detección automática externa  <br/> |SAN=lyncdiscover.\<sipdomain\>  <br/> |
   
Este SAN debe asignarse al certificado asignado al agente de escucha SSL en el proxy inverso.
  
> [!NOTE]
> El agente de escucha de proxy inverso va a tener SAN para las direcciones URL de los servicios web externos. Algunos ejemplos serían SAN=skypewebextpool01.contoso.com y dirwebexternal.contoso.com, si ha implementado el Director( que es opcional). 
  
## <a name="file-share"></a>Recurso compartido de archivos
<a name="Fileshare"> </a>

Skype Empresarial Server 2015 puede usar el mismo recurso compartido de archivos para todo el almacenamiento de archivos. Debe tener en cuenta lo siguiente:
  
- Un recurso compartido de archivos debe estar en almacenamiento conectado directo (DAS) o en una red de área de almacenamiento (SAN), lo que incluye el Sistema de archivos distribuido (DFS), así como una matriz redundante de discos independientes (RAID) para almacenes de archivos. Para obtener más información sobre DFS Windows Server 2012, consulte [esta página DFS](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/jj127250(v=ws.11)).
    
- Se recomienda un clúster compartido para el recurso compartido de archivos. Si usa uno, debe agrupar Windows Server 2012 o Windows Server 2012 R2. Windows Server 2008 R2 también es aceptable. ¿Por qué la última Windows? Es posible que las versiones anteriores no tengan los permisos adecuados para habilitar todas las características. Puede usar el Administrador de clústeres [](https://support.microsoft.com/help/224967/how-to-create-file-shares-on-a-cluster) para crear los recursos compartidos de archivos y este artículo Sobre cómo crear recursos compartidos de archivos en un clúster le ayudará con esos detalles.
    
> [!CAUTION] 
> Debe saber que no se admite el uso del almacenamiento conectado a la red (NAS) como recurso compartido de archivos, por lo que use una de las opciones enumeradas anteriormente. 
