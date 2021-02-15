---
title: 'Configurar controlador de borde de sesión: varios inquilinos'
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: Aprenda a configurar un controlador de borde de sesión (SBC) para que sirva a varios inquilinos para partners de Microsoft u operadores RTC.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: b81709b46774762036ba9465444d066a0adf019c
ms.sourcegitcommit: ac73536f790f83a61eeb2eb8c6b71662f7bd26fc
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/05/2021
ms.locfileid: "50110243"
---
# <a name="configure-a-session-border-controller-for-multiple-tenants"></a>Configurar un controlador de borde de sesión para varios inquilinos

El enrutamiento directo admite la configuración de un controlador de borde de sesión (SBC) para que sirva a varios inquilinos.

> [!NOTE]
> Este escenario está diseñado para partners y/o operadores RTC de Microsoft, denominados operadores más adelante en este documento. Un operador vende servicios de telefonía entregados a Microsoft Teams a sus clientes. 

Un operador:
- Implementa y administra un SBC en su centro de datos (los clientes no necesitan implementar un SBC y reciben servicios de telefonía del operador en el cliente de Teams).
- Interconecta la SBC a varios inquilinos.
- Proporciona servicios RTC a los clientes.
- Administra la calidad de las llamadas de un extremo a otro.
- Se cobra por separado para los servicios RTC.

Microsoft no administra los operadores. Microsoft ofrece un PBX (Sistema telefónico de Microsoft) y un cliente de Teams. Microsoft también certifica los teléfonos y certifica los SBC que se pueden usar con Microsoft Phone System. Antes de elegir un operador, asegúrese de que su elección tiene un SBC certificado y puede administrar la calidad de voz de un extremo a otro.

Estos son los pasos de implementación técnica para configurar el escenario.

**Solo el operador:**
1. Implemente el SBC y configúrelo para el escenario de hospedaje de acuerdo con las instrucciones de los proveedores [SBC certificados.](#deploy-and-configure-the-sbc)
2. Registre un nombre de dominio base en el inquilino del operador y solicite un certificado comodín.
3. Registra un subdominio de cada cliente, que forma parte del dominio base.

**Operador con un administrador global de clientes:**
1. Agregue el nombre del subdominio al inquilino del cliente.
2. Activar el nombre del subdominio.
3. Configure el tronco del operador para el inquilino del cliente y aprovisione los usuarios.

*Asegúrese de que comprende los conceptos básicos de DNS y cómo se administra el nombre de dominio en Microsoft 365 u Office 365. Revise [Obtener ayuda con los dominios de Microsoft 365 u Office 365](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) antes de continuar.*

## <a name="deploy-and-configure-the-sbc"></a>Implementar y configurar la SBC

Para conocer los pasos detallados sobre cómo implementar y configurar los SBC para un escenario de hospedaje de SBC, consulte la documentación del proveedor de SBC.

- **AudioCodes: Notas** de configuración de enrutamiento [directo,](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-Microsoft-Teams)la configuración del escenario de hospedaje SBC descrito en "Conexión de SBC de AudioCodes a Nota de configuración del modelo de hospedaje de enrutamiento directo de Microsoft Teams". 
- **Oracle: Notas** [de configuración de enrutamiento directo,](https://www.oracle.com/technetwork/indexes/documentation/acme-packet-2228107.html)la configuración del escenario de hospedaje SBC se describe en la sección "Microsoft". 
- **Comunicaciones de la cinta de opciones:**  Consulte la Guía de configuración de [SBC Core Microsoft Teams](https://support.sonus.net/display/IOT/PBXs+-+SBC+5k7kSWe) de la cinta de opciones para obtener documentación sobre cómo configurar las SBC de la serie básica de la cinta de opciones y, en esta página, Procedimiento recomendado de la cinta: Configuración de operadores para el enrutamiento directo de [SBC edge](https://support.sonus.net/display/UXDOC81/Connect+SBC+Edge+to+Microsoft+Teams+Direct+Routing+to+Support+Direct+Routing+Carrier) de Microsoft Teams
- **TE-Systems (anynode):**  Regístrate en la página de la comunidad de [TE-Systems](https://community.te-systems.de/) para obtener documentación y ejemplos sobre cómo configurar anynode SBC para varios inquilinos.
- **Metacambio:**  Regístrate en la [página de la comunidad de Metacambio](https://manuals.metaswitch.com/MAN39555) para obtener documentación sobre cómo habilitar Para varios inquilinos.

> [!NOTE]
> Preste atención a cómo configurar el encabezado "Contacto". El encabezado De contacto se usa para buscar el inquilino del cliente en el mensaje de invitación entrante. 

## <a name="register-a-base-domain-and-subdomains"></a>Registrar un dominio base y subdominios

Para el escenario de hospedaje, debe crear:
- Un nombre de dominio base propiedad del operador.
- Un subdominio que forma parte del nombre de dominio base en cada inquilino del cliente.

En el ejemplo siguiente:
- Adatum es un operador que sirve a varios clientes al proporcionar servicios de telefonía e Internet.
- Woodgrove Bank, Contoso y Adventure Works son tres clientes que tienen dominios de Microsoft 365 u Office 365 pero reciben los servicios de telefonía de Adatum.

Los **subdominios** DEBEN coincidir con el nombre FQDN del tronco que se configurará para el cliente y el FQDN en el encabezado de contacto al enviar la invitación a Microsoft 365 u Office 365. 

Cuando llega una llamada a la interfaz de enrutamiento directo de Microsoft 365 u Office 365, la interfaz usa el encabezado de contacto para buscar el inquilino donde debe buscarse el usuario. El enrutamiento directo no usa la búsqueda de números de teléfono en la invitación, ya que es posible que algunos clientes tengan números no DID que se puedan superponer en varios inquilinos. Por lo tanto, el nombre FQDN del encabezado de contacto es necesario para identificar el inquilino exacto que debe buscar el usuario por el número de teléfono.

*Consulte Obtener ayuda con los dominios de  [Office 365](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) para obtener más información sobre cómo crear nombres de dominio en organizaciones de Microsoft 365 u Office 365.*

En el siguiente diagrama se resumen los requisitos para basar el dominio, los subdominios y el encabezado de contacto.

![Diagrama que muestra los requisitos para los dominios y el encabezado de contacto](media/direct-routing-1-sbc-requirements.png)

La SBC requiere un certificado para autenticar las conexiones. Para el escenario de hospedaje de SBC, el operador debe solicitar un certificado con CN o SAN *\* .base_domain (por ejemplo, \* .customers.adatum.biz).* Este certificado se puede usar para autenticar las conexiones a varios inquilinos que se sirven desde un único SBC.


La tabla siguiente es un ejemplo de una configuración.


|Nuevo nombre de dominio |Tipo|Registrado  |Certificado CN/SAN para SBC  |Dominio predeterminado del espacio empresarial en el ejemplo  |Nombre FQDN que SBC debe presentar en el encabezado de contacto al enviar llamadas a usuarios|
|---------|---------|---------|---------|---------|---------|
|customers.adatum.biz|    Base     |     In carrier tenant  |    \*.customers.adatum.biz  |   adatum.biz      |NO, este es un inquilino de servicio, ningún usuario |
|sbc1.customers.adatum.biz|    Subdominio  |    En un inquilino de cliente  |    \*.customers.adatum.biz  | woodgrovebank.us  |  sbc1.customers.adatum.biz|
|sbc2.customers.adatum.biz  |   Subdominio | En un inquilino de cliente   |   \*.customers.adatum.biz   |contoso.com   |sbc2.customers.adatum.biz |
|sbc3.customers.adatum.biz |   Subdominio | En un inquilino de cliente |   \*.customers.adatum.biz  |  adventureworks.com | sbc3.customers.adatum.biz |
||         |         |         |         |         |

Para configurar la base y los subdominios, siga los pasos que se describen a continuación. En el ejemplo, configuraremos un nombre de dominio base (customers.adatum.biz) y un subdominio para un cliente (sbc1.customers.adatum.biz en el inquilino de Woodgrove Bank).

> [!NOTE]
> Use sbcX.customers.adatum.biz para habilitar la voz en el inquilino del operador. sbcX puede ser cualquier nombre de host alfanumérico único y válido.

## <a name="register-a-base-domain-name-in-the-carrier-tenant"></a>Registrar un nombre de dominio base en el inquilino del operador

**Estas acciones se realizan en el inquilino del operador.**

### <a name="ensure-that-you-have-appropriate-rights-in-the-carrier-tenant"></a>Asegúrese de que tiene los derechos adecuados en el inquilino del operador

Solo puede agregar nuevos dominios si ha iniciado sesión en el Centro de administración de Microsoft 365 como administrador global. 

Para validar el rol que tiene, inicie sesión en el Centro de administración de Microsoft 365 (, vaya a Usuarios activos y, a continuación, compruebe que tiene un rol de https://portal.office.com)   >  administrador global). 

Para obtener más información sobre los roles de administrador y cómo asignar un rol en Microsoft 365 u Office 365, vea Acerca de los [roles de administrador.](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d)

### <a name="add-a-base-domain-to-the-tenant-and-verify-it"></a>Agregar un dominio base al inquilino y comprobarlo

1. En el Centro de administración de Microsoft 365, vaya a **Configuración del**  >  **dominio Agregar**  >  **dominio.**
2. En el **cuadro Escriba un dominio de su propiedad,** escriba el FQDN del dominio base. En el ejemplo siguiente, el dominio base es *customers.adatum.biz.*

    ![Captura de pantalla que muestra la página Agregar un dominio](media/direct-routing-2-sbc-add-domain.png)

3. Haga clic en **Siguiente**.
4. En el ejemplo, el inquilino ya tiene un adatum.biz de dominio comprobado. El asistente no le pedirá comprobación adicional porque customers.adatum.biz un subdominio del nombre ya registrado. Sin embargo, si agrega un FQDN que no se ha comprobado antes, tendrá que pasar por el proceso de comprobación. El proceso de comprobación se [describe a continuación.](#add-a-subdomain-to-the-customer-tenant-and-verify-it)

    ![Captura de pantalla que muestra la confirmación de un nombre de dominio comprobado](media/direct-routing-3-sbc-verify-domain.png)

5. Haga **clic en** Siguiente y, en la página Actualizar configuración **DNS,** seleccione **Agregaré los** registros DNS por mi cuenta y haré clic en **Siguiente.**
6. En la página siguiente, borre todos los valores (a menos que desee usar el nombre de dominio para Exchange, SharePoint, o Teams/Skype Empresarial), haga clic en Siguiente **y,** a continuación, haga clic en **Finalizar.** Asegúrese de que el nuevo dominio se encuentra en el estado Configuración completada.

    ![Captura de pantalla que muestra dominios con el estado de Configuración completada](media/direct-routing-14-sbc-setup-complete.png)

### <a name="activate-the-domain-name"></a>Activar el nombre de dominio

Después de haber registrado un nombre de dominio, debe activarlo agregando al menos un usuario con licencia de Sistema telefónico y asignando una dirección SIP con la parte FQDN de la dirección SIP que coincida con el dominio base creado. La licencia puede revocarse después de la activación del dominio (pueden tardar hasta 24 horas).

> [!NOTE]
> El inquilino del operador debe tener al menos una licencia de Sistema telefónico asignada al inquilino para evitar la eliminación de la configuración de Skype Empresarial. 

*Consulte Obtener ayuda con dominios de [Microsoft 365 u Office 365](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) para obtener más información sobre cómo agregar usuarios de organizaciones de Microsoft 365 u Office 365.*

Por ejemplo: test@customers.adatum.biz

![Captura de pantalla de la página de activación del dominio base](media/direct-routing-4-sbc-domain-activation.png)

## <a name="register-a-subdomain-name-in-a-customer-tenant"></a>Registrar un nombre de subdominio en un inquilino de cliente

Necesitará crear un nombre de subdominio único para cada cliente. En este ejemplo, crearemos un subdominio en un sbc1.customers.adatum.biz inquilino con el nombre de dominio predeterminado woodgrovebank.us.

**Todas las acciones siguientes se encuentran en el inquilino del cliente.**

### <a name="ensure-that-you-have-appropriate-rights-in-the-customer-tenant"></a>Asegúrese de que tiene los derechos adecuados en el inquilino del cliente

Solo puede agregar nuevos dominios si ha iniciado sesión en el Centro de administración de Microsoft 365 como administrador global. 

Para validar el rol que tiene, inicie sesión en el Centro de administración de Microsoft 365 (, vaya a Usuarios activos y, a continuación, compruebe que tiene un rol de https://portal.office.com)   >  administrador global). 

Para obtener más información sobre los roles de administrador y cómo asignar un rol en Microsoft 365 u Office 365, vea Acerca de los [roles de administrador.](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d)

### <a name="add-a-subdomain-to-the-customer-tenant-and-verify-it"></a>Agregar un subdominio al inquilino del cliente y comprobarlo
1. En el Centro de administración de Microsoft 365, vaya a **Configuración del**  >  **dominio Agregar**  >  **dominio.**
2. En el cuadro Escriba un dominio de su **propiedad,** escriba el FQDN del subdominio para este espacio empresarial. En el ejemplo siguiente, el subdominio es sbc1.customers.adatum.biz.

    ![Captura de pantalla de la página Agregar un dominio](media/direct-routing-5-sbc-add-customer-domain.png)

3. Haga clic en **Siguiente**.
4. El FQDN nunca se ha registrado en el inquilino. En el paso siguiente, tendrá que comprobar el dominio. Seleccione **Agregar un registro TXT en su lugar.** 

    ![Captura de pantalla de la página Comprobar dominio](media/direct-routing-6-sbc-verify-customer-domain.png)

5. Haga **clic en** Siguiente y anote el valor TXT generado para comprobar el nombre de dominio.

    ![Captura de pantalla de registros de texto en la página Comprobar dominio](media/direct-routing-7-sbc-verify-domain-txt.png)

6. Cree el registro TXT con el valor del paso anterior en el proveedor de host DNS del operador.

    ![Captura de pantalla que muestra la creación del registro TXT](media/direct-routing-8-sbc-txt-record.png)

    Para obtener más información, consulte [Crear registros DNS en cualquier proveedor de host DNS.](https://support.office.com/article/create-dns-records-at-any-dns-hosting-provider-for-office-365-7b7b075d-79f9-4e37-8a9e-fb60c1d95166)

7. Vuelve al centro de administración de Microsoft 365 del cliente y haz clic en **Comprobar.** 
8. En la página siguiente, seleccione **Agregaré los registros DNS** yo mismo y haré clic en **Siguiente.**

    ![Captura de pantalla de las opciones de la página Actualizar configuración DNS](media/direct-routing-9-sbc-update-dns.png)

9. En la página **Elegir los servicios en línea,** desactive todas las opciones y haga clic en **Siguiente.**

    ![Captura de pantalla de la página Elegir los servicios en línea](media/direct-routing-10-sbc-choose-services.png)

10. Haga **clic en Finalizar** en la página Actualizar configuración **DNS.**

    ![Captura de pantalla de la página Actualizar configuración DNS](media/direct-routing-11-sbc-update-dns-finish.png)

11. Asegúrese de que el estado se **ha completado.** 
    
    ![Captura de pantalla de la página que muestra el estado de Configuración completada](media/direct-routing-12-sbc-setup-complete.png)
    
> [!NOTE]
> La dirección URL base y el subdominio del cliente individual tienen que estar en el mismo espacio empresarial para que pueda agregar un tronco _de ruta_ directa.

### <a name="activate-the-subdomain-name"></a>Activar el nombre del subdominio

Después de registrar un nombre de dominio, debe activarlo agregando al menos un usuario y asignando una dirección SIP con la parte del FQDN de la dirección SIP que coincida con el subdominio creado en el inquilino del cliente. La licencia puede revocarse del usuario después de la activación del subdominio (pueden tardar hasta 24 horas).

*Consulte Obtener ayuda con dominios de [Microsoft 365 u Office 365](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) para obtener más información sobre cómo agregar usuarios de organizaciones de Microsoft 365 u Office 365.*

Por ejemplo: test@sbc1.customers.adatum.biz

![Captura de pantalla de la página Activación de la subdominio](media/direct-routing-13-sbc-activate-subdomain.png)

### <a name="create-a-trunk-and-provision-users"></a>Crear un tronco y aprovisionar usuarios

Con la versión inicial de enrutamiento directo, Microsoft requería que se agregase un tronco a cada inquilino con servicio (inquilino del cliente) con New-CSOnlinePSTNGateway.

Sin embargo, esto no ha resultado óptimo por dos razones:
 
- **Administración de gastos generales.** Descargar o descargar un SBC, por ejemplo, cambia algunos parámetros, como habilitar o deshabilitar la omisión de medios. Para cambiar el puerto es necesario cambiar los parámetros de varios inquilinos (ejecutando Set-CSOnlinePSTNGateway), pero en realidad es el mismo SBC. 

-  **Procesamiento de sobrecarga.** Recopilación y supervisión de datos de mantenimiento de troncos: las opciones SIP recopiladas de varios troncos lógicos que son, en realidad, el mismo SBC y el mismo tronco físico, ralentizan el procesamiento de los datos de enrutamiento.
 
En función de estos comentarios, Microsoft aporta una nueva lógica para aprovisionar los troncos para los inquilinos del cliente.

Se introdujeron dos nuevas entidades:
-    Un tronco del transportista registrado en el inquilino del operador con el comando New-CSOnlinePSTNGateway, por ejemplo New-CSOnlinePSTNGateway -FQDN customers.adatum.biz -SIPSignalingport 5068 -ForwardPAI $true.

-    Un tronco derivado, que no requiere registro. Simplemente es un nombre de host que se agrega desde el tronco transportista. Deriva todos los parámetros de configuración del tronco transportista. No es necesario crear el tronco derivado en PowerShell y la asociación con el tronco transportista se basa en el nombre FQDN (consulte los detalles a continuación).

**Ejemplo y lógica de aprovisionamiento**

-    Los operadores solo necesitan configurar y administrar un solo tronco (tronco transportista en el dominio del transportista), mediante el comando Set-CSOnlinePSTNGateway empresa. En el ejemplo anterior se muestra adatum.biz;
-    En el inquilino del cliente, el operador solo necesita agregar el FQDN de tronco derivado a las directivas de enrutamiento de voz de los usuarios. No es necesario ejecutar ninguna New-CSOnlinePSTNGateway para un tronco.
-    El tronco derivado, como su nombre sugiere, hereda o deriva todos los parámetros de configuración del tronco transportista. Ejemplos:
-    Customers.adatum.biz: el tronco transportista que debe crearse en el inquilino del transportista.
-    Sbc1.customers.adatum.biz: el tronco derivado en un inquilino de cliente que no es necesario crear en PowerShell.  Simplemente puede agregar el nombre del tronco derivado en el inquilino del cliente en la directiva de enrutamiento de voz en línea sin crearlo.
-   El operador tendrá que configurar el registro DNS para resolver el FQDN de tronco derivado a la dirección ip SBC del operador.

-    Los cambios realizados en un tronco del transportista (en el inquilino del operador) se aplican automáticamente a los troncos derivados. Por ejemplo, los operadores pueden cambiar un puerto SIP en el tronco carrier y este cambio se aplica a todos los troncos derivados. La nueva lógica para configurar los troncos simplifica la administración ya que no necesita ir a cada inquilino y cambiar el parámetro en cada tronco.
-    Las opciones se envían solo al FQDN del tronco del transportista. El estado de mantenimiento del tronco transportista se aplica a todos los troncos derivados y se usa para decisiones de enrutamiento. Más información sobre las [opciones de enrutamiento directo.](https://docs.microsoft.com/microsoftteams/direct-routing-monitor-and-troubleshoot)
-    El transportista puede descargar el tronco transportista y todos los troncos derivados también se descargarán. 
 

**Migración del modelo anterior al tronco transportista**
 
Para la migración desde la implementación actual del modelo hospedado por el operador al nuevo modelo, los operadores tendrán que volver a configurar los troncos para los inquilinos del cliente. Quite los troncos de los inquilinos del cliente Remove-CSOnlinePSTNGateway (dejando el tronco en el inquilino del operador)-

Recomendamos encarecidamente migrar a la nueva solución lo antes posible, ya que mejoraremos la supervisión y el aprovisionamiento con el modelo de transportista y tronco derivado.
 

Consulte las instrucciones del [proveedor de SBC](#deploy-and-configure-the-sbc) sobre cómo configurar el envío del nombre del FQDN de los subdominios en el encabezado de contacto.

## <a name="considerations-for-setting-up-muti-tenant-failover"></a>Consideraciones para configurar la conmutación por error del inquilino muti 

Para configurar la conmutación por error para un entorno multiempresa, tendrá que hacer lo siguiente:

- Para cada inquilino, agregue los FQDN para dos SDC diferentes.  Por ejemplo:

   customer1.sbc1.contoso.com <br>
   customer1.sbc2.contoso.com <br>

- En las directivas de enrutamiento de voz en línea de los usuarios, especifique ambas BDC.  Si se produce un error en un SBC, la directiva de enrutamiento enruta las llamadas al segundo SBC.


## <a name="see-also"></a>Consulte también

[Planear el enrutamiento directo](direct-routing-plan.md)

[Configurar el enrutamiento directo](direct-routing-configure.md)
