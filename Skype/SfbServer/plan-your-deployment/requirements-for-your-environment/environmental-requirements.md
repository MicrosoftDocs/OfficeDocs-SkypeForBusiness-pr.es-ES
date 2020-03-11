---
title: Requisitos del entorno para Skype empresarial Server 2015
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
description: 'Resumen: Configure los requisitos que no son de servidor para Skype empresarial Server 2015. Hay varias cosas que querrá configurar antes de realizar la implementación, como Active Directory, DNS, Certs y Fileshares.'
ms.openlocfilehash: 164f4b8037c972907eb6d1375f77b3cc350959e5
ms.sourcegitcommit: 543f650ad4aff73bccfe7a60b66fb944b4e3c119
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/10/2020
ms.locfileid: "42572808"
---
# <a name="environmental-requirements-for-skype-for-business-server-2015"></a>Requisitos del entorno para Skype empresarial Server 2015
 
**Resumen:** Configure los requisitos que no son del servidor para Skype empresarial Server 2015. Hay varias cosas que querrá configurar antes de realizar la implementación, como Active Directory, DNS, Certs y Fileshares.
  
¿Qué es un requisito del entorno para Skype empresarial Server 2015? Pues bien, hemos colocado todo lo que no está directamente relacionado con este tema, por lo que no tiene que hacer clic en todo el tiempo. Si está buscando requisitos previos del servidor, puede consultar los [requisitos del servidor para Skype empresarial server 2015](server-requirements.md) doc. la[planeación de redes](../../plan-your-deployment/network-requirements/network-requirements.md) también se documenta por separado. De lo contrario, esto es lo que tenemos en este artículo:
  
- [Active Directory](environmental-requirements.md#AD)
  
- [Sistema de nombres de dominio (DNS)](environmental-requirements.md#DNS)
  
- [Certificados](environmental-requirements.md#Certs)
  
- [Recurso compartido de archivos](environmental-requirements.md#Fileshare)
  
## <a name="active-directory"></a>Active Directory
<a name="AD"> </a>

Mientras que muchos de los datos de configuración de servidores y servicios se almacenan en el almacén de administración central de Skype empresarial Server 2015, hay algunas cosas todavía almacenadas en Active Directory:
  
|**Objetos de Active Directory**|**Tipos de objeto**|
|:-----|:-----|
|Extensiones de esquema  <br/> |Extensiones de objetos de usuario  <br/> |
||Extensiones para Lync Server 2013 y Lync Server 2010, para mantener la compatibilidad con versiones anteriores compatibles con las versiones anteriores.  <br/> |
|Datos  <br/> |URI de SIP del usuario y otros parámetros de usuario  <br/> |
||Objetos de contacto de aplicaciones (como la aplicación de grupo de respuesta y la aplicación de operador de conferencia).  <br/> |
||Datos publicados para compatibilidad con versiones anteriores.  <br/> |
||Un punto de control de servicio (SCP) para el almacén de administración central.  <br/> |
||Cuenta de autenticación Kerberos (un objeto de equipo opcional).  <br/> |
   
### <a name="os-for-domain-controllers"></a>SO para controladores de dominio

Por lo tanto, ¿qué sistema operativo de controlador de dominio se puede usar? Tenemos la siguiente lista:

- Windows Server 2019 (debe tener la actualización acumulativa 5 o posterior de Skype empresarial Server 2015)
  
- Windows Server 2016
    
- Windows Server 2012 R2
    
- Windows Server 2012
    
- Windows Server 2008 R2
    
- Windows Server 2008
    
Ahora, el nivel funcional del dominio de cualquier dominio en el que implemente Skype empresarial Server 2015 y el nivel funcional del bosque de cualquier bosque en el que implemente Skype empresarial Server 2015 debe ser uno de los siguientes:

- Windows Server 2019 (debe tener la actualización acumulativa 5 o posterior de Skype empresarial Server 2015)
  
- Windows Server 2016
    
- Windows Server 2012 R2
    
- Windows Server 2012
    
- Windows Server 2008 R2
    
- Windows Server 2008
    
- Windows Server 2003
    
¿Puede tener controladores de dominio de solo lectura en estos entornos? Seguro, siempre y cuando también haya controladores de dominio grabables disponibles en el mismo sitio que Skype empresarial Server.
  
Ahora, es importante saber que Skype empresarial Server 2015 no admite dominios de etiqueta única. ¿Qué son? Si tiene un dominio raíz con la etiqueta contoso. local, eso será correcto. Si tiene un dominio raíz que acaba de denominarse local, eso no va a funcionar y no se admite como resultado. Un poco más sobre esto se ha escrito [en este artículo de Knowledge Base](https://support.microsoft.com/kb/300684/en-us).
  
Skype empresarial Server 2015 tampoco admite el cambio de nombre de dominios. Si tiene que hacerlo realmente, tendrá que desinstalar Skype empresarial Server 2015, realizar el cambio de nombre del dominio y, a continuación, volver a instalar Skype empresarial Server 2015.
  
Por último, es posible que esté tratando con un dominio con un entorno de AD DS bloqueado y que todo sea correcto. Tenemos más información sobre cómo implementar Skype empresarial Server 2015 en ese tipo de entorno en los documentos de implementación.
  
### <a name="ad-topologies"></a>Topologías de AD

Las topologías admitidas de Skype empresarial Server 2015 son:
  
- Un solo bosque con un solo dominio
    
- Un solo bosque con un solo árbol y varios dominios
    
- Un solo bosque con varios árboles y espacios de nombres separados
    
- Varios bosques en una topología de bosque central
    
- Varios bosques en una topología de bosque de recursos
    
- Varios bosques en una topología de bosque de recursos de Skype empresarial con Exchange Online
    
- Varios bosques en una topología de bosque de recursos con Skype empresarial online y Azure Active Directory Connect
    
Disponemos de diagramas y descripciones para ayudarle a determinar qué topología tiene en su entorno, o lo que necesita configurar antes de instalar Skype empresarial Server 2015. Para simplificarlo, también se incluye una clave:
  
![La es una clave para los iconos usados en los diagramas de topología de Skype empresarial](../../media/cc0dbc17-cf81-4b79-bf99-4614cc6828a0.png)
  
#### <a name="single-forest-with-single-domain"></a>Un solo bosque con un solo dominio

![Diagrama de un solo bosque de Active Directory con un solo dominio](../../media/24921a0b-3a3e-4bad-8427-49300e2e3f7a.png)
  
No es más sencillo que esto, es un bosque de dominio único, es una topología común.
  
#### <a name="single-forest-with-a-single-tree-and-multiple-domains"></a>Un solo bosque con un solo árbol y varios dominios

![Diagrama de un solo bosque, árbol único y dominios varios](../../media/63b9f0dd-6bac-4ba9-ae68-8be032d09dcb.png)
  
Este diagrama muestra un único bosque, pero también tiene uno o más dominios secundarios (hay tres en este ejemplo específico). Por lo tanto, el dominio en el que se crean los usuarios puede ser diferente del dominio en el que se implementa Skype empresarial Server 2015. ¿Por qué preocuparse por esto? Es importante recordar que, al implementar un grupo de servidores front-end de Skype empresarial Server, todos los servidores de ese grupo tienen que estar en un solo dominio. Puede tener administración entre dominios mediante el soporte de Skype empresarial Server para los grupos de administración universal de Windows.
  
De nuevo en el diagrama anterior, puede ver que los usuarios de un dominio pueden tener acceso a los grupos de servidores de Skype empresarial Server desde el mismo dominio o desde distintos dominios, incluso si dichos usuarios se encuentran en un dominio secundario.
  
#### <a name="single-forest-with-multiple-trees-and-disjoint-namespaces"></a>Un solo bosque con varios árboles y espacios de nombres separados

![Un solo bosque, varios árboles y un diagrama de espacios de nombres separados](../../media/5ede77a1-f5d2-499c-a2c8-d02f3c2f7cd7.png)
  
Es posible que tenga una topología similar a la de este diagrama, donde tiene un bosque, pero dentro de ese bosque hay varios dominios con espacios de nombres de AD independientes. Si ese es el caso, este diagrama es un buen ejemplo, ya que tenemos usuarios en tres dominios distintos que tienen acceso a Skype empresarial Server 2015. Las líneas sólidas indican que están accediendo a un grupo de Skype empresarial Server en su propio dominio, mientras que una línea discontinua indica que van a un grupo en un árbol diferente.
  
Como puede ver, los usuarios del mismo dominio, el mismo árbol o incluso un árbol distinto pueden obtener acceso a los grupos de forma satisfactoria.
  
#### <a name="multiple-forests-in-a-central-forest-topology"></a>Varios bosques en una topología de bosque central

![Diagrama de varios bosques en una topología de bosque central](../../media/fec40746-4254-4c84-86b9-aad4a616ea2f.png)
  
Skype empresarial Server 2015 admite varios bosques configurados en una topología de bosque central. Si no está seguro de lo que tiene, el bosque central de la topología usa objetos en él para representar a los usuarios en los otros bosques y hospeda cuentas de usuario para los usuarios del bosque.
  
¿Cómo funciona? Bueno, un producto de sincronización de directorios (como Forefront Identity Manager o FIM) administra las cuentas de usuario de su organización en su existencia. Cuando se crea o se elimina una cuenta de un bosque, el cambio se sincroniza con el contacto correspondiente en el bosque central.
  
Evidentemente, si la infraestructura de AD está en marcha, es posible que no sea fácil desplazarse por esta topología, pero si ya está allí o si todavía planea la infraestructura de bosque, esta puede ser una buena opción. Puede centralizar la implementación de Skype empresarial Server 2015 dentro de un solo bosque, mientras los usuarios pueden buscar, comunicar y ver la presencia de otros usuarios en cualquier bosque. Todas las actualizaciones de contactos de usuario se administran automáticamente con software de sincronización.
  
#### <a name="multiple-forests-in-a-skype-for-business-resource-forest-topology"></a>Varios bosques en una topología de bosque de recursos de Skype empresarial
<a name="BKMK_multipleforestopology"> </a>

![Varios bosques en un diagrama de topología de bosque de recursos](../../media/41efa3b6-d9e6-47df-992b-fefcfc39a80d.png)
  
También se admite una topología de bosque de recursos; es allí donde un bosque está dedicado a ejecutar las aplicaciones de servidor, como Microsoft Exchange Server y Skype empresarial Server 2015. Estos bosques de recursos también hospedan una representación sincronizada de objetos de usuario activos, pero ninguna cuenta de usuario habilitada para inicio de sesión. Por lo tanto, el bosque de recursos es un entorno de servicios compartidos para otros bosques en el que residen los objetos de usuario y tienen una relación de confianza de nivel de bosque con el bosque de recursos.
  
Tenga en cuenta que Exchange Server se puede implementar en el mismo bosque de recursos que Skype empresarial Server o en un bosque diferente.
  
Para implementar Skype empresarial Server 2015 en este tipo de topología, debe crear un objeto de usuario deshabilitado en el bosque de recursos para cada cuenta de usuario en los bosques de usuarios (si Microsoft Exchange Server ya está en el entorno, esto podría realizarse por usted). A continuación, necesitará una herramienta de sincronización de directorios (como Forefront Identity Manager o FIM) para administrar las cuentas de usuario a lo largo de su ciclo de vida.
  
#### <a name="multiple-forests-in-a-skype-for-business-resource-forest-topology-with-exchange-online"></a>Varios bosques en una topología de bosque de recursos de Skype empresarial con Exchange Online
<a name="BKMK_multipleforestopology"> </a>

Esta topología es similar a la topología descrita en [varios bosques en una topología de bosque de recursos de Skype empresarial](environmental-requirements.md#BKMK_multipleforestopology).
  
En esta topología, hay uno o varios bosques de usuarios y Skype empresarial Server se implementa en un bosque de recursos dedicado. Exchange Server puede implementarse localmente en el mismo bosque de recursos o en un bosque diferente y configurarse para el modo híbrido con Exchange Online, o los servicios de correo electrónico pueden ser proporcionados exclusivamente por Exchange Online para las cuentas locales. No hay ningún diagrama disponible para esta topología.
  
#### <a name="multiple-forests-in-a-resource-forest-topology-with-skype-for-business-online-and-azure-active-directory-connect"></a>Varios bosques en una topología de bosque de recursos con Skype empresarial online y Azure Active Directory Connect
<a name="BKMK_multipleforestopology"> </a>

![Muestra dos bosques de AD: un bosque de usuarios y un bosque de recursos. Los dos bosques tienen una relación de confianza. Se sincronizan con Office 365 mediante Azure AD Connect. Todos los usuarios están habilitados para Skype empresarial a través de Office 365.](../../media/6d54558d-8786-4ebf-90f6-55ae3fdb5ae7.jpg)
  
Con este escenario, hay varios bosques locales, con una topología de bosque de recursos. Existe una relación de plena confianza entre los bosques de Active Directory. La herramienta Azure Active Directory Connect se usa para sincronizar cuentas entre los bosques de usuarios locales y Office 365.
  
 La organización también tiene Office 365 y usa [Azure Active Directory Connect](https://go.microsoft.com/fwlink/p/?LinkId=614836) para sincronizar sus cuentas locales con Office 365. Los usuarios habilitados para Skype empresarial están habilitados a través de Office 365 y Skype empresarial online. Skype empresarial Server no está implementado localmente.
  
La autenticación de inicio de sesión único es proporcionada por una granja de servicios de Federación de Active Directory ubicada en el bosque de usuarios.
  
En este escenario, se admite la implementación de Exchange local, Exchange Online, una solución híbrida de Exchange o que no se implemente Exchange. (El diagrama muestra solo Exchange local, pero también se admiten todas las soluciones de Exchange).
  
#### <a name="multiple-forests-in-a-resource-forest-topology-with-hybrid-skype-for-business"></a>Varios bosques en una topología de bosque de recursos con una implementación híbrida de Skype empresarial
<a name="BKMK_multipleforestopology"> </a>

En este escenario, hay uno o varios bosques de usuarios locales y Skype empresarial se implementa en un bosque de recursos dedicado y está configurado para el modo híbrido con Skype empresarial online. Exchange Server se puede implementar de forma local en el mismo bosque de recursos o en un bosque diferente y puede configurarse para el entorno híbrido con Exchange Online. Como alternativa, los servicios de correo electrónico pueden ser proporcionados exclusivamente por Exchange Online para las cuentas locales.
  
Para obtener más información, vea [Configure a multi-Forest Environment for Hybrid Skype for Business](../../skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/configure-a-multi-forest-environment-for-hybrid.md).
  
## <a name="domain-name-system-dns"></a>Sistema de nombres de dominio (DNS)
<a name="DNS"> </a>

Skype empresarial Server 2015 requiere DNS, por los motivos siguientes:
  
- DNS permite que Skype empresarial Server 2015 detecte servidores o grupos de servidores internos, lo que permite la comunicación de servidor a servidor.
    
- DNS permite que los equipos cliente detecten el grupo de servidores front-end o el servidor Standard Edition que se usa para las transacciones SIP.
    
- Asocia direcciones URL sencillas para conferencias con los servidores que hospedan dichas conferencias.
    
- DNS permite que los usuarios externos y los equipos cliente se conecten a los servidores perimetrales, o el proxy inverso HTTP, para la mensajería instantánea (mi) o las conferencias.
    
- Permite que los dispositivos de comunicaciones unificadas (UC) que no se hayan registrado detecten el grupo de servidores front-end o el servidor Standard Edition que ejecuta el servicio Web de actualización de dispositivos para obtener actualizaciones y enviar registros.
    
- El uso de DNS permite que los clientes móviles detecten automáticamente recursos de servicios web sin que los usuarios tengan que escribir manualmente las direcciones URL en la configuración del dispositivo.
    
- Y se usa en el equilibrio de carga de DNS.
    
Es importante tener en cuenta que Skype empresarial Server 2015 no admite nombres de dominio internacionalizados (IDN).
  
Es muy importante recordar que cualquier nombre en DNS será idéntico al nombre de equipo configurado en cualquier servidor usado por Skype empresarial Server 2015. En concreto, no podemos tener ningún nombre corto en el entorno y deben tener FQDN para el generador de topologías.
  
Esto parece lógico para cualquier equipo ya unido a un dominio, pero si tiene un servidor perimetral que no está unido a su dominio, puede tener un valor predeterminado con un nombre corto, sin sufijo de dominio. Asegúrese de que no es el caso, ya sea en el DNS o en el servidor perimetral, o en cualquier servidor o grupo de servidores de Skype empresarial Server 2015, en la misma materia.
  
Y no usar definitivamente caracteres Unicode o guiones bajos. Los caracteres estándar (que son a-Z, a-z, 0-9 y guiones) son compatibles con las entidades de certificación públicas y DNS externas (tendrá que asignar los FQDN al SN en el certificado, no olvide), por lo que se hará una gran cantidad de Grief si se puede nombrar teniendo esto en cuenta.
  
Para obtener más información sobre los requisitos de DNS para redes, consulte la sección [redes](../../plan-your-deployment/network-requirements/network-requirements.md) de nuestra documentación de planeación.
  
## <a name="certificates"></a>Certificados
<a name="Certs"> </a>

Una de las cosas más importantes que puede hacer antes de la implementación es asegurarse de que tiene los certificados en orden. Skype empresarial Server 2015 necesita una infraestructura de clave pública (PKI) para las conexiones de seguridad de la capa de transporte (TLS) y seguridad de la capa de transporte mutua (MTLS). Básicamente, para comunicarse de forma segura de forma normalizada, Skype empresarial Server usa certificados emitidos por entidades de certificación (CA).
  
Estas son algunas de las cosas que Skype empresarial Server 2015 usa certificados para:
  
- Conexiones TLS entre clientes y servidores
    
- Conexiones MTLS entre servidores
    
- Federación mediante la detección automática de asociados de DNS
    
- Acceso de usuarios remotos a la mensajería instantánea (IM)
    
- Acceso de usuarios externos a sesiones de audio/vídeo (a/v), uso compartido de aplicaciones y conferencias
    
- Hablar con aplicaciones web y Outlook Web Access (OWA)
    
Por lo tanto, es necesario planear el certificado. Ahora, veamos una lista de algunas de las cosas que debe tener en cuenta al solicitar certificados:
  
- Todos los certificados de servidor deben admitir la autorización de servidor (EKU de servidor).
    
- Todos los certificados de servidor deben contener un punto de distribución CRL (CDP).
    
- Todos los certificados deben estar firmados con un algoritmo de firma compatible con el sistema operativo. Skype empresarial Server 2015 admite el conjunto de tamaños de compendio SHA-1 y SHA-2 (224, 256, 384 y 512 bits), y cumple o supera los requisitos del sistema operativo.
    
- La inscripción automática se admite para los servidores internos que ejecutan Skype empresarial Server 2015.
    
- La inscripción automática no es compatible con los servidores perimetrales de Skype empresarial Server 2015.
    
- Cuando envíe una solicitud de certificado web a una entidad de certificación de Windows Server 2003, deberá hacerlo desde un equipo que ejecute Windows Server 2003 con SP2 o Windows XP.
    
> [!NOTE]
> Aunque KB922706 proporciona compatibilidad para resolver problemas relacionados con la inscripción de certificados Web en una inscripción Web de Windows Server 2003 Certificate Services, no hace posible usar Windows Server 2008, Windows Vista o Windows 7 para solicitar un certificado de una CA de Windows Server 2003. 
  
> [!NOTE]
> No se admite el uso del algoritmo de firma RSASSA-PSS, lo que puede producir errores en los problemas de inicio de sesión y desvío de llamadas, entre otros. 

> [!NOTE]
> Skype empresarial Server 2015 no admite certificados CNG.
  
- Se admiten longitudes de clave de cifrado de 1024, 2048 y 4096. Se recomiendan longitudes de clave de 2048 y posteriores.
    
- El algoritmo de síntesis predeterminada, o firma de hash, es RSA. También se admiten los algoritmos ECDH_P256, ECDH_P384 y ECDH_P521.
    
Así que es mucho para pensar y, definitivamente, hay varios niveles de confort al solicitar certificados a una entidad de certificación. Le proporcionaremos algunas instrucciones más a continuación para que su planeación sea lo más sencilla posible.
  
### <a name="certificates-for-your-internal-servers"></a>Certificados para los servidores internos

Necesitará certificados para la mayoría de los servidores internos y lo más probable es que los obtenga de una CA interna (que se encuentra en uno de sus dominios). Si lo desea, puede solicitar estos certificados a una entidad de certificación externa (una que se encuentre en Internet). Si se pregunta qué entidad de certificación pública debe dirigirse, puede consultar la lista de [socios de certificados de comunicaciones unificadas](/SkypeForBusiness/certification/services-ssl) .
  
También necesitará certificados cuando Skype empresarial Server 2015 se comunique con otras aplicaciones y servidores, como Microsoft Exchange Server. Obviamente, esto tendrá que ser un certificado que puedan usar estas otras aplicaciones y servidores de una manera compatible. Skype empresarial Server 2015 y otros productos de Microsoft admiten el protocolo Open Authorization (OAuth) para la autenticación y autorización de servidor a servidor. Si está interesado en esto, tenemos un artículo de planificación adicional para OAuth y Skype empresarial Server 2015.
  
Skype empresarial Server 2015 también incluye soporte para (sin necesidad) certificados firmados con la función de hash criptográfica SHA-256. Para admitir el acceso externo mediante SHA-256, el certificado externo debe emitirlo una entidad de certificación pública mediante SHA-256.
  
Para probar y mantener cosas sencillas, hemos puesto en las siguientes tablas los requisitos de certificado para los servidores Standard Edition, los grupos de servidores front-end y otras funciones, con la contoso.com ficticia que se usa para ver ejemplos (probablemente usará algo). else para su entorno). Estos son todos los certificados de servidor web estándar, con claves privadas que no se pueden exportar. Algunos aspectos adicionales que deben tenerse en cuenta:
  
- El uso mejorado de clave (EKU) del servidor se configura automáticamente al usar el Asistente para certificados para solicitar certificados.
    
- Cada nombre descriptivo del certificado tiene que ser único en el almacén del equipo.
    
- Según los nombres de ejemplo que aparecen a continuación, si ha configurado sipinternal.contoso.com o sipexternal.contoso.com en su DNS, deben agregarse al nombre alternativo del firmante (SAN) del certificado.
    
Certificados para servidores Standard Edition:
  
|**Certificado**|**Nombre de sujeto/nombre común**|**Nombre alternativo de sujeto**|**Ejemplo**|**Comments**|
|:-----|:-----|:-----|:-----|:-----|
|Valor predeterminado  <br/> |FQDN del grupo de servidores  <br/> |FQDN del grupo de servidores y FQDN del servidor  <br/> Si hay varios dominios SIP y está habilitada la configuración automática de los clientes, el Asistente para certificados detectará y agregará los FQDN de todos los dominios SIP admitidos.  <br/> Si este grupo de servidores es el servidor de inicio automático de sesión de los clientes y se requiere una correspondencia exacta del sistema de nombres de dominio (DNS) en la directiva del grupo, necesitará también entradas para sip.sipdomain (para cada uno de los dominios SIP que tenga).  <br/> |SN = SE01. contoso. com; SAN = SE01. contoso. com  <br/> Si este grupo de servidores es el servidor de inicio automático de sesión de los clientes y se necesita una correspondencia exacta de DNS en la directiva del grupo, necesitará también SAN=sip.contoso.com; SAN=sip.fabrikam.com  <br/> |En el servidor Standard Edition de servidores Standard Edition, el FQDN del servidor es el mismo que el FQDN del grupo de servidores.  <br/> El asistente detecta todos los dominios SIP especificados durante la instalación y los agrega automáticamente al nombre alternativo de sujeto.  <br/> También puede usar este certificado para la autenticación de servidor a servidor.  <br/> |
|Web interno  <br/> |FQDN del servidor  <br/> |Cada uno de los siguientes elementos:  <br/> • FQDN Web interno (que es el mismo que el FQDN del servidor)  <br/> Y  <br/> • Cumplir con direcciones URL sencillas  <br/> • Dirección URL sencilla de acceso telefónico  <br/> • Dirección URL sencilla de administración  <br/> O BIEN  <br/> • Una entrada comodín para las direcciones URL sencillas  <br/> |SN = SE01. contoso. com; SAN = SE01. contoso. com; SAN = cumplir. contoso. com; SAN = cumplir. fabrikam. com; SAN = marcado. contoso. com; SAN = admin. contoso. com  <br/> Con un certificado de comodín:  <br/> SN = SE01. contoso. com; SAN = SE01. contoso. com; SAN =\*. contoso.com  <br/> |No puede invalidar el FQDN de la web interna en el generador de topologías.  <br/> Si tiene varias direcciones URL sencillas de reunirse, tiene que incluirlas todas como San.  <br/> Las entradas de comodín se admiten para las entradas de direcciones URL sencillas.  <br/> |
|Web externo  <br/> |FQDN del servidor  <br/> |Cada uno de los siguientes elementos:  <br/> • FQDN de Web externo  <br/> Y  <br/> • Dirección URL sencilla de acceso telefónico  <br/> • Cumplir direcciones URL sencillas por dominio SIP  <br/> O BIEN  <br/> • Una entrada comodín para las direcciones URL sencillas  <br/> |SN = SE01. contoso. com; SAN = webcon01. contoso. com; SAN = cumplir. contoso. com; SAN = cumplir. fabrikam. com; SAN = marcado. contoso. com  <br/> Con un certificado de comodín:  <br/> SN = SE01. contoso. com; SAN = webcon01. contoso. com; SAN =\*. contoso.com  <br/> |Si tiene varias direcciones URL sencillas de reunirse, tiene que incluirlas todas como nombres alternativos de sujeto.  <br/> Las entradas de comodín se admiten para las entradas de direcciones URL sencillas.  <br/> |
   
Certificados para servidores front-end en un grupo de servidores front-end:
  
|**Certificado**|**Nombre de sujeto/nombre común**|**Nombre alternativo de sujeto**|**Ejemplo**|**Comments**|
|:-----|:-----|:-----|:-----|:-----|
|Valor predeterminado  <br/> |FQDN del grupo de servidores  <br/> |FQDN del grupo de servidores y FQDN del servidor  <br/> Si hay varios dominios SIP y está habilitada la configuración automática de los clientes, el Asistente para certificados detectará y agregará los FQDN de todos los dominios SIP admitidos.  <br/> Si este grupo de servidores es el servidor de inicio automático de sesión de los clientes y se requiere una correspondencia exacta del sistema de nombres de dominio (DNS) en la directiva del grupo, necesitará también entradas para sip.sipdomain (para cada uno de los dominios SIP que tenga).  <br/> |SN = eepool. contoso. com; SAN = eepool. contoso. com; SAN = ee01. contoso. com  <br/> Si este grupo de servidores es el servidor de inicio automático de sesión de los clientes y se necesita una correspondencia exacta de DNS en la directiva del grupo, necesitará también SAN=sip.contoso.com; SAN=sip.fabrikam.com  <br/> |El asistente detecta todos los dominios SIP especificados durante la instalación y los agrega automáticamente al nombre alternativo de sujeto.  <br/> También puede usar este certificado para la autenticación de servidor a servidor.  <br/> |
|Web interno  <br/> |FQDN del grupo de servidores  <br/> |Cada uno de los siguientes elementos:  <br/> • FQDN de Web interno (que no es el mismo que el FQDN del servidor)  <br/> • FQDN del servidor  <br/> • FQDN del grupo de Skype empresarial  <br/> Y  <br/> • Cumplir con direcciones URL sencillas  <br/> • Dirección URL sencilla de acceso telefónico  <br/> • Dirección URL sencilla de administración  <br/> O BIEN  <br/> • Una entrada comodín para las direcciones URL sencillas  <br/> |SN = ee01. contoso. com; SAN = ee01. contoso. com; SAN = cumplir. contoso. com; SAN = cumplir. fabrikam. com; SAN = marcado. contoso. com; SAN = admin. contoso. com  <br/> Con un certificado de comodín:  <br/> SN = ee01. contoso. com; SAN = ee01. contoso. com; SAN =\*. contoso.com  <br/> |Si tiene varias direcciones URL sencillas de reunirse, tiene que incluirlas todas como nombres alternativos de sujeto.  <br/> Las entradas de comodín se admiten para las entradas de direcciones URL sencillas.  <br/> |
|Web externo  <br/> |FQDN del grupo de servidores  <br/> |Cada uno de los siguientes elementos:  <br/> • FQDN de Web externo  <br/> Y  <br/> • Dirección URL sencilla de acceso telefónico  <br/> • Dirección URL sencilla de administración  <br/> O BIEN  <br/> • Una entrada comodín para las direcciones URL sencillas  <br/> |SN = ee01. contoso. com; SAN = webcon01. contoso. com; SAN = cumplir. contoso. com; SAN = cumplir. fabrikam. com; SAN = marcado. contoso. com  <br/> Con un certificado de comodín:  <br/> SN = ee01. contoso. com; SAN = webcon01. contoso. com; SAN =\*. contoso.com  <br/> |Si tiene varias direcciones URL sencillas de reunirse, tiene que incluirlas todas como nombres alternativos de sujeto.  <br/> Las entradas de comodín se admiten para las entradas de direcciones URL sencillas.  <br/> |
   
Certificados para el Director:
  
|**Certificado**|**Nombre de sujeto/nombre común**|**Nombre alternativo de sujeto**|**Ejemplo**|
|:-----|:-----|:-----|:-----|
|Valor predeterminado  <br/> |Grupo de servidores Director  <br/> |FQDN del Director, FQDN del grupo de directores.  <br/> Si este grupo de servidores es el servidor de inicio automático de sesión de los clientes y se requiere una correspondencia exacta de DNS en la Directiva de grupo, necesitará también entradas para SIP. sipdomain (para cada dominio SIP que tenga).  <br/> |pool.contoso.com; SAN = dir01. contoso. com  <br/> Si este grupo de servidores del director es el servidor de inicio automático de sesión de los clientes y se necesita una correspondencia exacta de DNS en la directiva del grupo, necesitará también SAN=sip.contoso.com; SAN=sip.fabrikam.com  <br/> |
|Web interno  <br/> |FQDN del servidor  <br/> |Cada uno de los siguientes elementos:  <br/> • FQDN Web interno (que es el mismo que el FQDN del servidor)  <br/> • FQDN del servidor  <br/> • FQDN del grupo de Skype empresarial  <br/> Y  <br/> • Cumplir con direcciones URL sencillas  <br/> • Dirección URL sencilla de acceso telefónico  <br/> • Dirección URL sencilla de administración  <br/> O BIEN  <br/> • Una entrada comodín para las direcciones URL sencillas  <br/> |SN = dir01. contoso. com; SAN = dir01. contoso. com; SAN = cumplir. contoso. com; SAN = cumplir. fabrikam. com; SAN = marcado. contoso. com; SAN = admin. contoso. com  <br/> Con un certificado de comodín:  <br/> SN = dir01. contoso. com; SAN = dir01. contoso. com SAN =\*. contoso.com  <br/> |
|Web externo  <br/> |FQDN del servidor  <br/> |Cada uno de los siguientes elementos:  <br/> • FQDN de Web externo  <br/> Y  <br/> • Cumplir direcciones URL sencillas por dominio SIP  <br/> • Dirección URL sencilla de acceso telefónico  <br/> O BIEN  <br/> • Una entrada comodín para las direcciones URL sencillas  <br/> |El FQDN Web externo del Director debe ser diferente del grupo de servidores front-end o del servidor front-end.  <br/> SN = dir01. contoso. com; SAN = directorwebcon01. contoso. com SAN = meet. contoso. com; SAN = cumplir. fabrikam. com; SAN = marcado. contoso. com  <br/> Con un certificado de comodín:  <br/> SN = dir01. contoso. com; SAN = directorwebcon01. contoso. com SAN =\*. contoso.com  <br/> |
   
Certificados para un servidor de mediación independiente:
  
|**Certificado**|**Nombre de sujeto/nombre común**|**Nombre alternativo de sujeto**|**Ejemplo**|
|:-----|:-----|:-----|:-----|
|Valor predeterminado  <br/> |FQDN del grupo de servidores  <br/> |FQDN del grupo de servidores  <br/> FQDN del servidor miembro del grupo  <br/> |SN = medsvr-pool.contoso.net; SAN = medsvr-pool.contoso.net; SAN = medsvr01. contoso. net  <br/> |
   
Certificados para una aplicación de sucursal con funciones de supervivencia:
  
|**Certificado**|**Nombre de sujeto/nombre común**|**Nombre alternativo de sujeto**|**Ejemplo**|
|:-----|:-----|:-----|:-----|
|Valor predeterminado  <br/> |FQDN de la aplicación  <br/> |SIP. \<sipdomain\> (solo necesita una entrada por dominio SIP)  <br/> |SN = sba01. contoso. net; SAN = SIP. contoso. com; SAN = SIP. fabrikam. com  <br/> |
   
### <a name="certificates-for-your-persistent-chat-server"></a>Certificados para el servidor de chat persistente

Al instalar el servidor de chat persistente, necesitará un certificado emitido por la misma entidad de certificación que el usado por sus servidores internos de Skype empresarial Server 2015. Esto debe realizarse en cada servidor que ejecute los servicios Web de chat persistente para la carga y descarga de archivos. Se recomienda encarecidamente disponer de los certificados necesarios antes de iniciar la instalación del chat persistente, y si la entidad de certificación es externa, aún más (esto puede tardar un poco de tiempo en ser emitida).
  
### <a name="certificates-for-external-user-access-edge"></a>Certificados para el acceso de usuarios externos (perimetral)

Skype empresarial Server 2015 admite el uso de un **único certificado público** para interfaces externas perimetrales de acceso y conferencia Web, además del servicio de autenticación a/V, que se proporciona a través del servidor perimetral. Normalmente, la interfaz perimetral interna usará un certificado privado emitido por la entidad de certificación interna, pero si lo prefiere, también puede usar un certificado público para esto, si procede de una CA de confianza.
  
El proxy inverso (RP) también va a usar un certificado público y cifra la comunicación desde el RP a los clientes, y el RP a los servidores internos mediante HTTP (o más concretamente, TLS a través de HTTP).
  
### <a name="certificates-for-mobility"></a>Certificados para movilidad

Si va a implementar la movilidad y va a admitir la detección automática para clientes móviles, necesitará incluir entradas de nombre alternativo de sujeto adicionales en los certificados para admitir conexiones seguras desde los clientes móviles.
  
¿Qué certificados? Necesitará nombres de SAN para la detección automática en los certificados aquí:
  
- Grupo de servidores Director
    
- Grupo de servidores front-end
    
- Proxy inverso
    
Enumeraremos los detalles en cada una de las tablas siguientes.
  
Ahora, aquí es donde un poco de preplanificación es bueno, pero a veces ha implementado Skype empresarial Server 2015 sin intención de implementar la movilidad, y esto se enciende en la línea cuando ya tiene certificados en su entorno. Volver a emitirlos a través de una entidad de certificación interna suele ser bastante fácil, pero con certificados públicos de una entidad de certificación pública, puede ser un poco más caro.
  
Si eso es lo que busca y tiene una gran cantidad de dominios SIP (lo que haría que la adición de SANS resultara más costosa), puede configurar el proxy inverso para que use HTTP para la solicitud de servicio Detección automática inicial, en lugar de usar HTTPS (que es el valor predeterminado configuración). El tema Planning for Mobility tiene más información al respecto.
  
Requisitos de certificado de grupo de servidores de director y grupo de servidores front-end:
  
|**Descripción**|**Entrada de SAN**|
|:-----|:-----|
|Dirección URL interna del servicio Detección automática  <br/> |SAN = lyncdiscoverinternal. \<sipdomain\>  <br/> |
|Dirección URL externa del servicio Detección automática  <br/> |SAN = lyncdiscover. \<sipdomain\>  <br/> |
   
También puede usar SAN =\*. \<sipdomain\>
  
Requisitos de certificado de proxy inverso (CA pública):
  
|**Descripción**|**Entrada de SAN**|
|:-----|:-----|
|Dirección URL externa del servicio Detección automática  <br/> |SAN = lyncdiscover. \<sipdomain\>  <br/> |
   
Este SAN debe asignarse al certificado asignado a la escucha de SSL en el proxy inverso.
  
> [!NOTE]
> Su escucha de proxy inverso va a tener San para las direcciones URL de los servicios web externos. Algunos ejemplos serían SAN = skypewebextpool01. contoso. com y dirwebexternal.contoso.com, si ha implementado el director (que es opcional). 
  
## <a name="file-share"></a>Recurso compartido de archivos
<a name="Fileshare"> </a>

Skype empresarial Server 2015 puede usar el mismo recurso compartido de archivos para todo el almacenamiento de archivos. Debe tener en cuenta lo siguiente:
  
- Un recurso compartido de archivos debe estar en un almacenamiento de conexión directa (DAS) o en una red de área de almacenamiento (SAN), lo que incluye el sistema de archivos distribuido (DFS), así como una matriz redundante de discos independientes (RAID) para los almacenes de archivos. Para obtener más información sobre DFS para Windows Server 2012, consulte [esta página DFS](https://technet.microsoft.com/library/jj127250.aspx).
    
- Se recomienda un clúster compartido para el recurso compartido de archivos. Si está usando uno, debe agrupar Windows Server 2012 o Windows Server 2012 R2. Windows Server 2008 R2 también es aceptable. ¿Por qué la última ventana? Es posible que las versiones anteriores no tengan los permisos adecuados para habilitar todas las características. Puede usar el administrador de clústeres para crear los recursos compartidos de archivos y este [procedimiento para crear recursos compartidos de archivos en un artículo de clúster](https://support.microsoft.com/help/224967/how-to-create-file-shares-on-a-cluster) le ayudará con estos detalles.
    
> [!CAUTION] 
> Debe saber que no se admite el uso de almacenamiento conectado a la red (NAS) como un recurso compartido de archivos; por ello, use una de las opciones enumeradas anteriormente. 
  
