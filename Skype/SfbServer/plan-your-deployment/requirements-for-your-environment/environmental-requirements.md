---
title: Requisitos del entorno para Skype Empresarial Server 2015
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
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 4812c444-2546-48d7-9ca7-b71fce508ed8
description: 'Resumen: configure los requisitos que no son de servidor para Skype Empresarial Server 2015. Hay una variedad de cosas que querrá configurar antes de realizar la implementación, como Active Directory, DNS, certificados y archivos compartidos.'
ms.openlocfilehash: 83e01cec8bea5a45debadcf8ef9167ddd53b6a46
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832140"
---
# <a name="environmental-requirements-for-skype-for-business-server-2015"></a>Requisitos del entorno para Skype Empresarial Server 2015
 
**Resumen:** Configure los requisitos que no son de servidor para Skype Empresarial Server 2015. Hay una variedad de cosas que querrá configurar antes de realizar la implementación, como Active Directory, DNS, certificados y archivos compartidos.
  
¿Cuál es un requisito del entorno para Skype Empresarial Server 2015? Hemos puesto todo lo que no está relacionado directamente con el servidor en este tema, por lo que no tiene que hacer tanto clic. Si está buscando requisitos previos del servidor, puede consultar el documento Requisitos del [](../../plan-your-deployment/network-requirements/network-requirements.md) servidor para [Skype Empresarial Server 2015.](server-requirements.md) La planeación de redes también se documenta por separado. De lo contrario, esto es lo que tenemos en este artículo:
  
- [Active Directory](environmental-requirements.md#AD)
  
- [Sistema de nombres de dominio (DNS)](environmental-requirements.md#DNS)
  
- [Certificados](environmental-requirements.md#Certs)
  
- [Recurso compartido de archivos](environmental-requirements.md#Fileshare)
  
## <a name="active-directory"></a>Active Directory
<a name="AD"> </a>

Aunque muchos datos de configuración para servidores y servicios se almacenan en el almacén de administración central de Skype Empresarial Server 2015, hay algunas cosas que aún se almacenan en Active Directory:
  
|**Objetos de Active Directory**|**Tipos de objeto**|
|:-----|:-----|
|Extensiones de esquema  <br/> |Extensiones de objetos de usuario  <br/> |
||Extensiones para Lync Server 2013 y Lync Server 2010, para mantener la compatibilidad con versiones anteriores admitidas.  <br/> |
|Datos  <br/> |URI de SIP del usuario y otros parámetros de usuario  <br/> |
||Objetos de contacto para aplicaciones (como la aplicación Grupo de respuesta y la aplicación Operador de conferencia).  <br/> |
||Datos publicados para compatibilidad con versiones anteriores.  <br/> |
||Un punto de control de servicio (SCP) para el almacén de administración central.  <br/> |
||Cuenta de autenticación Kerberos (un objeto de equipo opcional).  <br/> |
   
### <a name="os-for-domain-controllers"></a>Sistema operativo para controladores de dominio

Por lo tanto, ¿qué sistema operativo del controlador de dominio se puede usar? Tenemos la siguiente lista:

- Windows Server 2019 (debe tener la actualización acumulativa 5 o posterior de Skype Empresarial Server 2015)
  
- Windows Server 2016
    
- Windows Server 2012 R2
    
- Windows Server 2012
    
- Windows Server 2008 R2
    
- Windows Server 2008
    
Ahora, el nivel funcional de dominio de cualquier dominio en el que implemente Skype Empresarial Server 2015 y el nivel funcional de bosque de cualquier bosque en el que implemente Skype Empresarial Server 2015 deben ser uno de los siguientes:

- Windows Server 2019 (debe tener la actualización acumulativa 5 o posterior de Skype Empresarial Server 2015)
  
- Windows Server 2016
    
- Windows Server 2012 R2
    
- Windows Server 2012
    
- Windows Server 2008 R2
    
- Windows Server 2008
    
- Windows Server 2003
    
¿Puede tener controladores de dominio de solo lectura en estos entornos? Seguro, siempre y cuando también haya controladores de dominio grabables disponibles en el mismo sitio que Skype Empresarial Server.
  
Ahora, es importante saber que Skype Empresarial Server 2015 no admite dominios con una sola etiqueta. ¿Qué son? Si tiene un dominio raíz con la etiqueta contoso.local, estará bien. Si tiene un dominio raíz que simplemente se denomina local, eso no funcionará y, como resultado, no se admite. Se ha escrito un poco más sobre esto [en este artículo de Knowledge Base.](https://support.microsoft.com/kb/300684/en-us)
  
Skype Empresarial Server 2015 tampoco admite el cambio de nombre de dominios. If you've really got to do that, then you'll need to uninstall Skype for Business Server 2015, do the domain rename, and then reinstall Skype for Business Server 2015.
  
Por último, es posible que esté trabajando con un dominio con un entorno de AD DS bloqueado y todo está bien. Tenemos más información sobre cómo implementar Skype Empresarial Server 2015 en ese tipo de entorno en los documentos de implementación.
  
### <a name="ad-topologies"></a>Topologías de AD

Las topologías compatibles de Skype Empresarial Server 2015 son:
  
- Un solo bosque con un solo dominio
    
- Un solo bosque con un solo árbol y varios dominios
    
- Un solo bosque con varios árboles y espacios de nombres separados
    
- Varios bosques en una topología de bosque central
    
- Varios bosques en una topología de bosque de recursos
    
- Varios bosques en una topología de bosque de recursos de Skype Empresarial con Exchange Online
    
- Varios bosques en una topología de bosque de recursos con Skype Empresarial Online y Azure Active Directory Connect
    
Tenemos diagramas y descripciones que le ayudarán a determinar qué topología tiene en su entorno o qué puede que necesite configurar antes de instalar Skype Empresarial Server 2015. Para que sea sencillo, también estamos incluyendo una clave:
  
![Es una clave para los iconos usados para los diagramas de topología de Skype Empresarial](../../media/cc0dbc17-cf81-4b79-bf99-4614cc6828a0.png)
  
#### <a name="single-forest-with-single-domain"></a>Un solo bosque con un solo dominio

![Diagrama del bosque único de Active Directory con un solo dominio](../../media/24921a0b-3a3e-4bad-8427-49300e2e3f7a.png)
  
No es más fácil que esto, es un bosque de dominio único, es una topología común.
  
#### <a name="single-forest-with-a-single-tree-and-multiple-domains"></a>Un solo bosque con un solo árbol y varios dominios

![Un solo bosque, un solo árbol y un diagrama de dominios mutiple](../../media/63b9f0dd-6bac-4ba9-ae68-8be032d09dcb.png)
  
Este diagrama muestra un solo bosque, de nuevo, pero también tiene uno o más dominios secundarios (hay tres en este ejemplo específico). Por lo tanto, el dominio en el que se crean los usuarios puede ser diferente del dominio en el que se implementa Skype Empresarial Server 2015. ¿Por qué preocuparse por esto? Es importante recordar que al implementar un grupo de servidores front-end de Skype Empresarial Server, todos los servidores de ese grupo deben estar en un solo dominio. Puede tener una administración entre dominios a través de la compatibilidad de Skype Empresarial Server con los grupos de administradores universales de Windows.
  
De vuelta al diagrama anterior, puede ver que los usuarios de un dominio pueden acceder a los grupos de Skype Empresarial Server desde el mismo dominio o desde dominios diferentes, incluso si esos usuarios están en un dominio secundario.
  
#### <a name="single-forest-with-multiple-trees-and-disjoint-namespaces"></a>Un solo bosque con varios árboles y espacios de nombres separados

![Diagrama de un solo bosque, varios árboles y espacios de nombres distintos](../../media/5ede77a1-f5d2-499c-a2c8-d02f3c2f7cd7.png)
  
Puede ser que tenga una topología similar a este diagrama, donde tiene un bosque, pero dentro de ese bosque hay varios dominios, con espacios de nombres de AD independientes. Si ese es el caso, este diagrama es una buena ilustración, ya que tenemos usuarios en tres dominios diferentes que tienen acceso a Skype Empresarial Server 2015. Las líneas sólidas indican que están accediendo a un grupo de Skype Empresarial Server en su propio dominio, mientras que una línea discontinua indica que van a un grupo de servidores en un árbol diferente por completo.
  
Como puede ver, los usuarios del mismo dominio, el mismo árbol o incluso un árbol diferente pueden tener acceso a los grupos de servidores correctamente.
  
#### <a name="multiple-forests-in-a-central-forest-topology"></a>Varios bosques en una topología de bosque central

![Varios bosques en un diagrama de topología de bosque central](../../media/fec40746-4254-4c84-86b9-aad4a616ea2f.png)
  
Skype Empresarial Server 2015 admite varios bosques configurados en una topología de bosque central. Si no está seguro de que es lo que tiene, el bosque central de la topología usa objetos en él para representar a los usuarios de los otros bosques y hospeda cuentas de usuario para cualquier usuario del bosque.
  
¿Cómo funciona? Bien, un producto de sincronización de directorios (como Forefront Identity Manager o FIM) administra las cuentas de usuario de su organización a lo largo de su existencia. Cuando se crea o elimina una cuenta de un bosque, ese cambio se sincroniza con el contacto correspondiente en el bosque central.
  
Claramente, si la infraestructura de AD se está trasladando a esta topología puede que no sea fácil, pero si ya está allí o sigue planeando la infraestructura del bosque, esta puede ser una buena opción. Puede centralizar la implementación de Skype Empresarial Server 2015 en un solo bosque, mientras que los usuarios pueden buscar, comunicarse y ver la presencia de otros usuarios en cualquier bosque. Todas las actualizaciones de contactos de usuario se controlan automáticamente con software de sincronización.
  
#### <a name="multiple-forests-in-a-skype-for-business-resource-forest-topology"></a>Varios bosques en una topología de bosque de recursos de Skype Empresarial
<a name="BKMK_multipleforestopology"> </a>

![Varios bosques en un diagrama de topología de bosque de recursos](../../media/41efa3b6-d9e6-47df-992b-fefcfc39a80d.png)
  
También se admite una topología de bosque de recursos; es donde un bosque se dedica a ejecutar las aplicaciones de servidor, como Microsoft Exchange Server y Skype Empresarial Server 2015. Estos bosques de recursos también hospedan una representación sincronizada de objetos de usuario activos, pero no cuentas de usuario habilitadas para inicio de sesión. Por lo tanto, el bosque de recursos es un entorno de servicios compartidos para otros bosques en los que residen objetos de usuario y tienen una relación de confianza de nivel de bosque con el bosque de recursos.
  
Tenga en Exchange Server puede implementarse en el mismo bosque de recursos que Skype Empresarial Server o en un bosque diferente.
  
Para implementar Skype Empresarial Server 2015 en este tipo de topología, crearía un objeto de usuario deshabilitado en el bosque de recursos para cada cuenta de usuario de los bosques de usuarios (si Microsoft Exchange Server ya está en el entorno, esto puede hacerse automáticamente). A continuación, necesitará una herramienta de sincronización de directorios (como Forefront Identity Manager o FIM) para administrar cuentas de usuario durante su ciclo de vida.
  
#### <a name="multiple-forests-in-a-skype-for-business-resource-forest-topology-with-exchange-online"></a>Varios bosques en una topología de bosque de recursos de Skype Empresarial con Exchange Online
<a name="BKMK_multipleforestopology"> </a>

Esta topología es similar a la topología descrita en Varios bosques en una topología de bosque de recursos [de Skype Empresarial.](environmental-requirements.md#BKMK_multipleforestopology)
  
En esta topología, hay uno o más bosques de usuarios y Skype Empresarial Server se implementa en un bosque de recursos dedicado. Exchange Server puede implementarse localmente en el mismo bosque de recursos o en un bosque diferente y configurarse para la implementación híbrida con Exchange Online, o exchange Online puede proporcionar servicios de correo electrónico exclusivamente para las cuentas locales. No hay ningún diagrama disponible para esta topología.
  
#### <a name="multiple-forests-in-a-resource-forest-topology-with-skype-for-business-online-and-azure-active-directory-connect"></a>Varios bosques en una topología de bosque de recursos con Skype Empresarial Online y Azure Active Directory Connect
<a name="BKMK_multipleforestopology"> </a>

![Muestra dos bosques de AD, un bosque de usuarios y un bosque de recursos. Los dos bosques tienen una relación de confianza. Se sincronizan con Microsoft 365 u Office 365 con Azure AD Connect. Todos los usuarios están habilitados para Skype Empresarial a través de Microsoft 365 u Office 365.](../../media/6d54558d-8786-4ebf-90f6-55ae3fdb5ae7.jpg)
  
Con este escenario, hay varios bosques locales, con una topología de bosque de recursos. Hay una relación de plena confianza entre los bosques de Active Directory. La herramienta Azure Active Directory Connect se usa para sincronizar cuentas entre los bosques de usuarios locales y Microsoft 365 u Office 365.
  
 La organización también tiene Microsoft 365 u Office 365 y usa [Azure Active Directory Connect](https://go.microsoft.com/fwlink/p/?LinkId=614836) para sincronizar sus cuentas locales con Microsoft 365 u Office 365. Los usuarios habilitados para Skype Empresarial se habilitan a través de Microsoft 365 u Office 365 y Skype Empresarial Online. Skype Empresarial Server no está implementado localmente.
  
La autenticación de inicio de sesión único la proporciona una granja de servicios de federación de Active Directory ubicada en el bosque de usuarios.
  
En este escenario, se admite la implementación de Exchange local, Exchange Online, una solución híbrida de Exchange o no tener Exchange implementado en absoluto. (El diagrama muestra solo Exchange local, pero las otras soluciones de Exchange también son totalmente compatibles).
  
#### <a name="multiple-forests-in-a-resource-forest-topology-with-hybrid-skype-for-business"></a>Varios bosques en una topología de bosque de recursos con Skype Empresarial híbrido
<a name="BKMK_multipleforestopology"> </a>

En este escenario, hay uno o más bosques de usuarios locales y Skype Empresarial se implementa en un bosque de recursos dedicado y está configurado para el modo híbrido con Skype Empresarial Online. Exchange Server puede implementarse localmente en el mismo bosque de recursos o en un bosque diferente y se puede configurar para la implementación híbrida con Exchange Online. Como alternativa, Exchange Online puede proporcionar exclusivamente los servicios de correo electrónico para las cuentas locales.
  
Para obtener más información, vea [Configurar un entorno de varios bosques para Skype Empresarial híbrido.](../../skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/configure-a-multi-forest-environment-for-hybrid.md)
  
## <a name="domain-name-system-dns"></a>Sistema de nombres de dominio (DNS)
<a name="DNS"> </a>

Skype Empresarial Server 2015 requiere DNS, por los siguientes motivos:
  
- DNS permite a Skype Empresarial Server 2015 detectar servidores internos o grupos de servidores, lo que permite las comunicaciones de servidor a servidor.
    
- DNS permite a los equipos cliente detectar el grupo de servidores front-end o el servidor Standard Edition que se usa para las transacciones SIP.
    
- Asocia direcciones URL sencillas para conferencias con los servidores que hospedan dichas conferencias.
    
- DNS permite que los usuarios externos y los equipos cliente se conecten a los servidores perimetrales, o al proxy inverso HTTP, para mensajería instantánea (MI) o conferencias.
    
- Permite a los dispositivos de comunicaciones unificadas (UC) que no hayan iniciado sesión detectar el grupo de servidores front-end o el servidor Standard Edition que ejecuta el servicio web de actualización de dispositivos para obtener actualizaciones y enviar registros.
    
- El uso de DNS permite a los clientes móviles detectar automáticamente recursos de servicios web sin necesidad de que los usuarios escriban manualmente direcciones URL en la configuración del dispositivo.
    
- Y se usa en el equilibrio de carga de DNS.
    
Es importante tener en cuenta que Skype Empresarial Server 2015 no admite nombres de dominio internacionalizados (IDN).
  
Y es muy importante recordar que cualquier nombre en DNS es idéntico al nombre del equipo configurado en cualquier servidor que esté utilizando Skype Empresarial Server 2015. En concreto, no podemos tener nombres cortos en el entorno y debemos tener FQDN para topology Builder.
  
Parece que sería lógico para cualquier equipo que ya esté unido a un dominio, pero si tiene un servidor perimetral que no está unido a su dominio, puede tener un nombre corto predeterminado, sin sufijo de dominio. Asegúrese de que ese no es el caso, ya sea en DNS o en el servidor perimetral, o en cualquier servidor o grupo de Skype Empresarial Server 2015, en ese caso.
  
Y definitivamente no use caracteres Unicode ni caracteres de subrayado. Los caracteres estándar (que son A-Z, a-z, 0-9 y guiones) son los que van a ser compatibles con DNS externos y las autoridades de certificación públicas (tendrá que asignar FQDN al SN en el certificado, no lo olvide), por lo que se ahorrará mucho pesar si tiene esto en cuenta.
  
Para obtener más información sobre los requisitos dns para redes, consulte la [sección Redes](../../plan-your-deployment/network-requirements/network-requirements.md) de nuestra documentación de planeación.
  
## <a name="certificates"></a>Certificados
<a name="Certs"> </a>

Una de las cosas más importantes que puede hacer antes de la implementación es asegurarse de que tiene los certificados en orden. Skype Empresarial Server 2015 necesita una infraestructura de clave pública (PKI) para la seguridad de la capa de transporte (TLS) y las conexiones de seguridad de la capa de transporte mutua (MTLS). Básicamente, para comunicarse de forma segura de forma estandarizada, Skype Empresarial Server usa certificados emitidos por las autoridades de certificación (CA).
  
Estos son algunos de los aspectos para los que Skype Empresarial Server 2015 usa certificados:
  
- Conexiones TLS entre clientes y servidores
    
- Conexiones MTLS entre servidores
    
- Federación mediante la detección automática basada en DNS de los socios
    
- Acceso de usuarios remotos a la mensajería instantánea (IM)
    
- Acceso de usuarios externos a sesiones de audio y vídeo (AV), uso compartido de aplicaciones y conferencias
    
- Hablar con aplicaciones web y Outlook Web Access (OWA)
    
Por lo tanto, la planeación de certificados es imprescindible. Ahora, echemos un vistazo a una lista de algunas de las cosas que debe tener en cuenta al solicitar certificados:
  
- Todos los certificados de servidor deben admitir la autorización de servidor (EKU de servidor).
    
- Todos los certificados de servidor deben contener un punto de distribución CRL (CDP).
    
- Todos los certificados deben estar firmados mediante un algoritmo de firma admitido por el sistema operativo. Skype Empresarial Server 2015 admite el conjunto de aplicaciones SHA-1 y SHA-2 de tamaños de resumen (224, 256, 384 y 512 bits) y cumple o supera los requisitos del sistema operativo.
    
- La inscripción automática es compatible con los servidores internos que ejecutan Skype Empresarial Server 2015.
    
- La inscripción automática no es compatible con los servidores perimetrales de Skype Empresarial Server 2015.
    
- Cuando envíe una solicitud de certificado web a una entidad de certificación de Windows Server 2003, deberá hacerlo desde un equipo que ejecute Windows Server 2003 con SP2 o Windows XP.
    
> [!NOTE]
> Aunque KB922706 proporciona compatibilidad para resolver problemas relacionados con la inscripción de certificados web en una inscripción web de Servicios de certificados de Windows Server 2003, no permite usar Windows Server 2008, Windows Vista o Windows 7 para solicitar un certificado a una CA de Windows Server 2003. 
  
> [!NOTE]
> El uso del algoritmo de firma RSASSA-PSS no es compatible y puede provocar errores en el inicio de sesión y el reenvío de llamadas, entre otros problemas. 

> [!NOTE]
> Skype Empresarial Server 2015 no admite certificados CNG.
  
- Se admiten longitudes de clave de cifrado de 1024, 2048 y 4096. Se recomiendan longitudes clave de 2048 y superiores.
    
- El algoritmo predeterminado de síntesis o firma hash es RSA. También ECDH_P256, ECDH_P384 y ECDH_P521 algoritmos.
    
Por lo tanto, eso es mucho para pensar y, definitivamente, hay una variedad de niveles de comodidad con la solicitud de certificados de una CA. A continuación le proporcionaremos más instrucciones para que su planificación sea lo más sencilla posible.
  
### <a name="certificates-for-your-internal-servers"></a>Certificados para los servidores internos

Necesitará certificados para la mayoría de los servidores internos y lo más probable es que los obtenga de una CA interna (que se encuentra en su dominio). Si lo desea, puede solicitar estos certificados a una CA externa (una ubicada en Internet). Si se está preguntando a qué ENTIDAD pública debe ir, puede consultar la lista de asociados de certificados [de comunicaciones](/SkypeForBusiness/certification/services-ssl) unificadas.
  
También necesitará certificados cuando Skype Empresarial Server 2015 se comunique con otras aplicaciones y servidores, como Microsoft Exchange Server. Obviamente, esto tendrá que ser un certificado que estas otras aplicaciones y servidores puedan usar de forma compatible. Skype Empresarial Server 2015 y otros productos de Microsoft admiten el protocolo open authorization (OAuth) para la autenticación y autorización de servidor a servidor. Si está interesado en esto, tenemos un artículo de planeación adicional para OAuth y Skype Empresarial Server 2015.
  
Skype Empresarial Server 2015 también admite (sin necesidad) certificados firmados con la función hash criptográfica SHA-256. Para admitir el acceso externo mediante SHA-256, una CA pública debe emitir el certificado externo mediante SHA-256.
  
Para intentar que todo sea sencillo, hemos incluido los requisitos de certificado para servidores Standard Edition, grupos de servidores front-end y otros roles en las tablas siguientes, con el contoso.com ficticio que se usa para ejemplos (probablemente usará algo más para su entorno). Estos son todos certificados de servidor web estándar, con claves privadas que no son exportables. Algunos aspectos adicionales a tener en cuenta:
  
- El uso mejorado de claves (EKU) del servidor se configura automáticamente cuando se usa el asistente para certificados para solicitar certificados.
    
- Cada nombre descriptivo del certificado debe ser único en el almacén del equipo.
    
- Según los nombres de ejemplo siguientes, si ha configurado sipinternal.contoso.com o sipexternal.contoso.com en su DNS, deben agregarse al nombre alternativo de sujeto (SAN) del certificado.
    
Certificados para servidores Standard Edition:
  
|**Certificado**|**Nombre de sujeto/nombre común**|**Nombre alternativo de sujeto**|**Ejemplo**|**Comments**|
|:-----|:-----|:-----|:-----|:-----|
|Predeterminado  <br/> |FQDN del grupo de servidores  <br/> |FQDN del grupo de servidores y FQDN del servidor  <br/> Si hay varios dominios SIP y está habilitada la configuración automática de los clientes, el Asistente para certificados detectará y agregará los FQDN de todos los dominios SIP admitidos.  <br/> Si este grupo de servidores es el servidor de inicio automático de sesión de los clientes y se requiere una correspondencia exacta del sistema de nombres de dominio (DNS) en la directiva del grupo, necesitará también entradas para sip.sipdomain (para cada uno de los dominios SIP que tenga).  <br/> |SN=se01.contoso.com; SAN=se01.contoso.com  <br/> Si este grupo de servidores es el servidor de inicio automático de sesión de los clientes y se necesita una correspondencia exacta de DNS en la directiva del grupo, necesitará también SAN=sip.contoso.com; SAN=sip.fabrikam.com  <br/> |En el servidor Standard Edition, el FQDN del servidor es igual que el FQDN del grupo de servidores.  <br/> El asistente detecta los dominios SIP especificados durante la instalación y los agrega automáticamente como nombres alternativos de sujeto.  <br/> También puede usar este certificado para la autenticación de servidor a servidor.  <br/> |
|Web interno  <br/> |FQDN del servidor  <br/> |Cada uno de los siguientes elementos:  <br/> • FQDN web interno (que es el mismo que el FQDN del servidor)  <br/> Y  <br/> • Reunirse con direcciones URL sencillas  <br/> • Dirección URL sencilla de acceso telefónico  <br/> • Dirección URL sencilla de administración  <br/> O  <br/> • Una entrada de comodín para las direcciones URL sencillas  <br/> |SN=se01.contoso.com; SAN=se01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com; SAN=admin.contoso.com  <br/> Con un certificado de comodín:  <br/> SN=se01.contoso.com; SAN=se01.contoso.com; SAN= \* .contoso.com  <br/> |No puede invalidar el FQDN web interno en el Generador de topologías.  <br/> Si tiene varias direcciones URL sencillas de reunión, tiene que incluirlas todas como SAN.  <br/> Las entradas de comodín se admiten para las entradas de direcciones URL sencillas.  <br/> |
|Web externo  <br/> |FQDN del servidor  <br/> |Cada uno de los siguientes elementos:  <br/> • FQDN web externo  <br/> Y  <br/> • Dirección URL sencilla de acceso telefónico  <br/> • Reunir direcciones URL sencillas por dominio SIP  <br/> O  <br/> • Una entrada de comodín para las direcciones URL sencillas  <br/> |SN=se01.contoso.com; SAN=webcon01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com  <br/> Con un certificado de comodín:  <br/> SN=se01.contoso.com; SAN=webcon01.contoso.com; SAN= \* .contoso.com  <br/> |Si tiene varias direcciones URL sencillas de reunión, tiene que incluirlas todas como nombres alternativos de sujeto.  <br/> Las entradas de comodín se admiten para las entradas de direcciones URL sencillas.  <br/> |
   
Certificados para servidores front-end en un grupo de servidores front-end Enterprise Edition:
  
|**Certificado**|**Nombre de sujeto/nombre común**|**Nombre alternativo de sujeto**|**Ejemplo**|**Comments**|
|:-----|:-----|:-----|:-----|:-----|
|Predeterminado  <br/> |FQDN del grupo de servidores  <br/> |FQDN del grupo de servidores y FQDN del servidor  <br/> Si hay varios dominios SIP y está habilitada la configuración automática de los clientes, el Asistente para certificados detectará y agregará los FQDN de todos los dominios SIP admitidos.  <br/> Si este grupo de servidores es el servidor de inicio automático de sesión de los clientes y se requiere una correspondencia exacta del sistema de nombres de dominio (DNS) en la directiva del grupo, necesitará también entradas para sip.sipdomain (para cada uno de los dominios SIP que tenga).  <br/> |SN=eepool.contoso.com; SAN=eepool.contoso.com; SAN=ee01.contoso.com  <br/> Si este grupo de servidores es el servidor de inicio automático de sesión de los clientes y se necesita una correspondencia exacta de DNS en la directiva del grupo, necesitará también SAN=sip.contoso.com; SAN=sip.fabrikam.com  <br/> |El asistente detecta todos los dominios SIP especificados durante la instalación y los agrega automáticamente al nombre alternativo de sujeto.  <br/> También puede usar este certificado para la autenticación de servidor a servidor.  <br/> |
|Web interno  <br/> |FQDN del grupo de servidores  <br/> |Cada uno de los siguientes elementos:  <br/> • FQDN web interno (que NO es el mismo que el FQDN del servidor)  <br/> • FQDN del servidor  <br/> • FQDN del grupo de skype empresarial  <br/> Y  <br/> • Reunirse con direcciones URL sencillas  <br/> • Dirección URL sencilla de acceso telefónico  <br/> • Dirección URL sencilla de administración  <br/> O  <br/> • Una entrada de comodín para las direcciones URL sencillas  <br/> |SN=ee01.contoso.com; SAN=ee01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com; SAN=admin.contoso.com  <br/> Con un certificado de comodín:  <br/> SN=ee01.contoso.com; SAN=ee01.contoso.com; SAN= \* .contoso.com  <br/> |Si tiene varias direcciones URL sencillas de reunión, tiene que incluirlas todas como nombres alternativos de sujeto.  <br/> Las entradas de comodín se admiten para las entradas de direcciones URL sencillas.  <br/> |
|Web externo  <br/> |FQDN del grupo de servidores  <br/> |Cada uno de los siguientes elementos:  <br/> • FQDN web externo  <br/> Y  <br/> • Dirección URL sencilla de acceso telefónico  <br/> • Dirección URL sencilla de administración  <br/> O  <br/> • Una entrada de comodín para las direcciones URL sencillas  <br/> |SN=ee01.contoso.com; SAN=webcon01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com  <br/> Con un certificado de comodín:  <br/> SN=ee01.contoso.com; SAN=webcon01.contoso.com; SAN= \* .contoso.com  <br/> |Si tiene varias direcciones URL sencillas de reunión, tiene que incluirlas todas como nombres alternativos de sujeto.  <br/> Las entradas de comodín se admiten para las entradas de direcciones URL sencillas.  <br/> |
   
Certificados para el director:
  
|**Certificado**|**Nombre de sujeto/nombre común**|**Nombre alternativo de sujeto**|**Ejemplo**|
|:-----|:-----|:-----|:-----|
|Predeterminado  <br/> |Grupo de servidores Director  <br/> |FQDN del director, FQDN del grupo de directores.  <br/> Si este grupo es el servidor de inicio de sesión automático para los clientes y se requiere una coincidencia de DNS estricta en la directiva de grupo, también necesitará entradas para sip.sipdomain (para cada dominio SIP que tenga).  <br/> |pool.contoso.com; SAN=dir01.contoso.com  <br/> Si este grupo de servidores del director es el servidor de inicio automático de sesión de los clientes y se necesita una correspondencia exacta de DNS en la directiva del grupo, necesitará también SAN=sip.contoso.com; SAN=sip.fabrikam.com  <br/> |
|Web interno  <br/> |FQDN del servidor  <br/> |Cada uno de los siguientes elementos:  <br/> • FQDN web interno (que es el mismo que el FQDN del servidor)  <br/> • FQDN del servidor  <br/> • FQDN del grupo de skype empresarial  <br/> Y  <br/> • Reunirse con direcciones URL sencillas  <br/> • Dirección URL sencilla de acceso telefónico  <br/> • Dirección URL sencilla de administración  <br/> O  <br/> • Una entrada de comodín para las direcciones URL sencillas  <br/> |SN=dir01.contoso.com; SAN=dir01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com; SAN=admin.contoso.com  <br/> Con un certificado de comodín:  <br/> SN=dir01.contoso.com; SAN=dir01.contoso.com SAN= \* .contoso.com  <br/> |
|Web externo  <br/> |FQDN del servidor  <br/> |Cada uno de los siguientes elementos:  <br/> • FQDN web externo  <br/> Y  <br/> • Reunir direcciones URL sencillas por dominio SIP  <br/> • Dirección URL sencilla de acceso telefónico  <br/> O  <br/> • Una entrada de comodín para las direcciones URL sencillas  <br/> |El FQDN web externo del director debe ser diferente del grupo de servidores front-end o del servidor front-end.  <br/> SN=dir01.contoso.com; SAN=directorwebcon01.contoso.com SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com  <br/> Con un certificado de comodín:  <br/> SN=dir01.contoso.com; SAN=directorwebcon01.contoso.com SAN= \* .contoso.com  <br/> |
   
Certificados para servidor de mediación independiente:
  
|**Certificado**|**Nombre de sujeto/nombre común**|**Nombre alternativo de sujeto**|**Ejemplo**|
|:-----|:-----|:-----|:-----|
|Predeterminado  <br/> |FQDN del grupo de servidores  <br/> |FQDN del grupo de servidores  <br/> FQDN del servidor miembro del grupo de servidores  <br/> |SN=medsvr-pool.contoso.net; SAN=medsvr-pool.contoso.net; SAN=medsvr01.contoso.net  <br/> |
   
Certificados para la aplicación de sucursal con funciones de supervivencia:
  
|**Certificado**|**Nombre de sujeto/nombre común**|**Nombre alternativo de sujeto**|**Ejemplo**|
|:-----|:-----|:-----|:-----|
|Predeterminado  <br/> |FQDN de la aplicación  <br/> |SIP.\<sipdomain\> (Solo necesita una entrada por dominio SIP)  <br/> |SN=sba01.contoso.net; SAN=sip.contoso.com; SAN=sip.fabrikam.com  <br/> |
   
### <a name="certificates-for-your-persistent-chat-server"></a>Certificados para el servidor de chat persistente

Al instalar el servidor de chat persistente, necesitará un certificado emitido por la misma CA que el que usan los servidores internos de Skype Empresarial Server 2015. Esto debe hacerse para cada servidor que ejecute servicios web de chat persistente para la carga y descarga de archivos. Le recomendamos encarecidamente que tenga los certificados necesarios antes de iniciar la instalación de chat persistente y, si su CA es externa, aún más (estas cosas pueden tardar un poco en emitirse).
  
### <a name="certificates-for-external-user-access-edge"></a>Certificados para el acceso de usuarios externos (perimetral)

Skype Empresarial Server 2015 admite el uso de un único certificado público para interfaces perimetrales externas de acceso y conferencia web, además del servicio de autenticación A/V, que se proporciona **a** través de los servidores perimetrales. La interfaz interna perimetral normalmente usará un certificado privado emitido por la CA interna, pero si lo prefiere, también puede usar un certificado público para esto, si es de una CA de confianza.
  
El proxy inverso (RP) también va a usar un certificado público y cifra la comunicación de su RP a los clientes, y el RP a los servidores internos mediante HTTP (o más exactamente, TLS sobre HTTP).
  
### <a name="certificates-for-mobility"></a>Certificados para movilidad

Si va a implementar la movilidad y admite la detección automática para clientes móviles, tendrá que incluir algunas entradas de nombre alternativo de sujeto adicionales en los certificados para admitir las conexiones seguras de los clientes móviles.
  
¿Qué certificados? Necesitará nombres SAN para la detección automática en los certificados aquí:
  
- Grupo de servidores Director
    
- Grupo de servidores front-end
    
- Proxy inverso
    
Enumeraremos los detalles de cada tabla a continuación.
  
Ahora, aquí es donde un poco de planeación previa es buena, pero a veces ha implementado Skype Empresarial Server 2015 sin tener intención de implementar la movilidad, y eso viene hacia abajo cuando ya tiene certificados en su entorno. Volver a emitirlos a través de una CA interna suele ser bastante fácil, pero con certificados públicos de una CA pública, esto puede ser un poco más caro.
  
Si eso es lo que está viendo y si tiene muchos dominios SIP (lo que encarecería la adición de SANS), puede configurar el proxy inverso para que use HTTP para la solicitud inicial del servicio de detección automática, en lugar de usar HTTPS (que es la configuración predeterminada). El tema Planeación de movilidad tiene más información sobre esto.
  
Requisitos de certificado de grupo de directores y grupo de servidores front-end:
  
|**Descripción**|**Entrada de SAN**|
|:-----|:-----|
|Url del servicio Detección automática interna  <br/> |SAN=lyncdiscoverinternal.\<sipdomain\>  <br/> |
|Url del servicio de detección automática externa  <br/> |SAN=lyncdiscover.\<sipdomain\>  <br/> |
   
También puede usar SAN= \* .\<sipdomain\>
  
Requisitos de certificado de proxy inverso (CA pública):
  
|**Descripción**|**Entrada de SAN**|
|:-----|:-----|
|Url del servicio de detección automática externa  <br/> |SAN=lyncdiscover.\<sipdomain\>  <br/> |
   
Este SAN debe asignarse al certificado asignado a la escucha de SSL en el proxy inverso.
  
> [!NOTE]
> El agente de escucha de proxy inverso va a tener SAN para las direcciones URL de los servicios web externos. Algunos ejemplos serían SAN=skypewebextpool01.contoso.com y dirwebexternal.contoso.com, si ha implementado el director (que es opcional). 
  
## <a name="file-share"></a>Recurso compartido de archivos
<a name="Fileshare"> </a>

Skype Empresarial Server 2015 puede usar el mismo recurso compartido de archivos para todo el almacenamiento de archivos. Debe tener en cuenta lo siguiente:
  
- Un recurso compartido de archivos debe estar en almacenamiento conectado directo (DAS) o en una red de área de almacenamiento (SAN), lo que incluye el Sistema de archivos distribuido (DFS), así como una matriz redundante de discos independientes (RAID) para almacenes de archivos. Para obtener más información sobre DFS para Windows Server 2012, echa un vistazo [a esta página DFS.](https://technet.microsoft.com/library/jj127250.aspx)
    
- Se recomienda un clúster compartido para el recurso compartido de archivos. Si usas uno, debes agrupar Windows Server 2012 o Windows Server 2012 R2. Windows Server 2008 R2 también es aceptable. ¿Por qué la versión más reciente de Windows? Es posible que las versiones anteriores no tengan los permisos adecuados para habilitar todas las características. Puede usar el administrador de clústeres [](https://support.microsoft.com/help/224967/how-to-create-file-shares-on-a-cluster) para crear los recursos compartidos de archivos y este artículo sobre cómo crear recursos compartidos de archivos en un clúster le ayudará con esos detalles.
    
> [!CAUTION] 
> Debes saber que no se admite el uso de almacenamiento conectado a la red (NAS) como recurso compartido de archivos, por lo que usa una de las opciones enumeradas anteriormente. 
  
