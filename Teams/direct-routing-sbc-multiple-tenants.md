---
title: Configurar un controlador de borde de sesión para varios inquilinos
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
search.appverid: MET150
ms.collection: ''
description: Obtenga información sobre cómo configurar un controlador de borde de sesión (SBC) para servir a varios inquilinos.
ms.openlocfilehash: 3073800a6c200bcaeffafb557d6ea149dee598cd
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2018
ms.locfileid: "23866462"
---
# <a name="configure-a-session-border-controller-for-multiple-tenants"></a>Configurar un controlador de borde de sesión para varios inquilinos

Enrutamiento directo admite configurar una sesión de controlador de borde (SBC) para servir a varios inquilinos.

> [!NOTE]
> Este escenario está diseñada para los socios de Microsoft o los operadores de RTC, denominados operadores más adelante en este documento. Una compañía vende entregados a Microsoft Teams a sus clientes de servicios de telefonía. 

Un operador:
- Implemente y administre un SBC en su centro de datos (no es necesario implementar un SBC los clientes, y que reciben los servicios de telefonía de la compañía en el cliente de los equipos).
- Interconexiones la SBC para varios inquilinos.
- Proporciona servicios de RTC a los clientes.
- Administra la calidad de las llamadas de un extremo a otro.
- Cargos por separado para los servicios de RTC.

Microsoft no administra los operadores. Microsoft ofrece un sistema PBX (sistema de teléfono de Microsoft) y un cliente de los equipos, certifica teléfonos y certifica SBCs que se pueden usar con el sistema de teléfono de Microsoft. Antes de elegir un operador, por favor, asegúrese de que su elección tiene un SBC certificado y puede administrar la calidad de voz de un extremo a otro.

Los siguientes son los pasos de implementación técnica para configurar el escenario.

**Sólo del proveedor:**
1. Implementar la SBC y configurarlo para el escenario de hospedaje según las [instrucciones de los proveedores SBC certificadas](#deploy-and-configure-the-sbc).
2. Registrar un nombre de dominio base en el inquilino de portadora y solicitar un certificado comodín.
3. Registrar un subdominio para cada cliente, que forma parte del dominio base.

**Operador con un administrador Global de cliente:**
1. Agregue el nombre de subdominio para el inquilino del cliente.
2. Activar el nombre de subdominio.
3. Configure el tronco en la compañía a los usuarios de inquilinos y aprovisionamiento de cliente.

*Por favor, asegúrese de que comprende los conceptos básicos DNS y cómo se administra el nombre de dominio en Office 365. [Obtener ayuda con Office 365 dominios](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) se revise antes de continuar.*

## <a name="deploy-and-configure-the-sbc"></a>Implementar y configurar el SBC

Para obtener instrucciones detalladas acerca de cómo implementar y configurar SBCs para un escenario de hospedaje de SBC, hacer referencia a la documentación del proveedor SBC.

- **AudioCodes:** [Notas de configuración de enrutamiento directo](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-Microsoft-Teams), la configuración de la SBC que hospeda el escenario descrito en "Connecting AudioCodes SBC a Microsoft Teams directa enrutamiento Hosting modelo configuración Nota". 
- **La cinta de opciones Communications:** Para escenarios de hospedaje de SBC, se admite solo la serie de núcleo. Consulte la [Guía de configuración de los equipos de Microsoft de la cinta de opciones Communications SBC principales](https://support.sonus.net/display/IOT/PBXs+-+SBC+5k7kSWe).

> [!NOTE]
> Por favor, preste atención a cómo configurar el encabezado "Contacto". El encabezado de contacto se usa para buscar al inquilino del cliente en el mensaje de invitación entrante. 

## <a name="register-a-base-domain-and-subdomains"></a>Registrar un dominio base y subdominios

Para el escenario de hospedaje, debe crear:
- Un nombre de dominio base que pertenecen a la compañía.
- Un subdominio que forma parte del nombre de dominio base en cada inquilino del cliente.

En el ejemplo siguiente:
- Adatum es un operador que sirve de varios clientes proporcionando servicios de Internet y telefonía.
- Woodgrove Bank, Contoso y Adventure Works son tres los clientes que tienen dominios de Office 365 pero que reciben los servicios de telefonía de Adatum.

Subdominios **debe** coincidir con el nombre FQDN del tronco que se configuran para el cliente y el FQDN en el encabezado de contacto al enviar la invitación a Office 365. 

Cuando una llamada llega a la interfaz de enrutamiento directo de Office 365, la interfaz utiliza el encabezado de contacto para buscar al inquilino donde el usuario debe ser consultado. Enrutamiento directas no usar búsqueda de número de teléfono en la invitación, que algunos clientes podrían tener que no sean-números que pueden se superponen en varios inquilinos DID. Por lo tanto, es necesario el nombre FQDN en el encabezado de contacto para identificar el inquilino exacto para buscar el usuario por el número de teléfono.

*Revise [obtener ayuda con los dominios de Office 365](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) para obtener más información sobre la creación de nombres de dominio en los inquilinos de Office 365.*

El diagrama siguiente resume los requisitos de dominio base, subdominios y encabezado de contacto.

![Requisitos de dominio base, subdominios y encabezado de contacto](media/direct-routing-1-sbc-requirements.png)

La SBC requiere un certificado para autenticar las conexiones. Para el escenario de hospedaje de SBC, el operador debe solicitar un certificado con SAN * \*.base_domain (por ejemplo, \*customers.adatum.biz)*. Este certificado puede usarse para autenticar las conexiones a varios inquilinos procesadas por un SBC único.

La tabla siguiente es un ejemplo de una configuración.


|Nuevo nombre de dominio |Tipo|Registrado  |Certificado SAN de SBC  |Dominio de inquilinos predeterminado en el ejemplo  |Nombre del FQDN que debe presentar SBC en el encabezado de contacto al enviar las llamadas a los usuarios|
|---------|---------|---------|---------|---------|---------|
|Customers.adatum.biz|    Base     |     En el inquilino de operador  |    \*. customers.adatum.biz  |   adatum.biz      |NA, este es un inquilino de servicio, ningún usuario |
|sbc1.Customers.adatum.biz|    Subdominio  |    En un inquilino del cliente  |    \*. customers.adatum.biz  | woodgrovebank.us  |  sbc1.Customers.adatum.biz|
|sbc2.Customers.adatum.biz  |   Subdominio | En un inquilino del cliente   |   \*. customers.adatum.biz   |contoso.com   |sbc2.Customers.adatum.biz |
|sbc3.Customers.adatum.biz |   Subdominio | En un inquilino del cliente |   \*. customers.adatum.biz  |  AdventureWorks.com | sbc3.Customers.adatum.biz |
||         |         |         |         |         |

Para configurar la base y subdominios, siga los pasos descritos a continuación. En el ejemplo, se configurará un nombre de dominio base (customers.adatum.biz) y un subdominio para un cliente (sbc1.customers.adatum.biz en el inquilino de Woodgrove Bank).

## <a name="register-a-base-domain-name-in-the-carrier-tenant"></a>Registrar un nombre de dominio base en el inquilino de operador

**Estas acciones se realizan en el inquilino de operador.**

### <a name="ensure-that-you-have-appropriate-rights-in-the-carrier-tenant"></a>Asegúrese de que tiene los derechos adecuados en el inquilino de operador

Sólo se pueden agregar nuevos dominios si ha iniciado sesión el centro de administración de Office 365 como un administrador Global. 

Para validar el rol que tiene, inicie sesión en el centro de administración de Microsoft 365 (https://portal.office.com), vaya a **los usuarios** > **Usuarios activos**y, a continuación, compruebe que dispone de una función de administrador Global. 

Para obtener más información acerca de los roles de administrador y cómo asignar una función de Office 365, vea [roles de administrador acerca de Office 365](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d).

### <a name="add-a-base-domain-to-the-tenant-and-verify-it"></a>Agregar un dominio de la base para el inquilino y compruebe

1.  En el centro de administración de Microsoft 365, vaya al **programa de instalación** > **dominios** > **Agregue el dominio**.
2.  En el cuadro **Escriba un dominio que es propietario** , escriba el FQDN del dominio base. En el siguiente ejemplo, el dominio de la base es *customers.adatum.biz*.

    ![Adición de un dominio base](media/direct-routing-2-sbc-add-domain.png)

3. Haga clic en **Siguiente**.
4. En el ejemplo, el inquilino ya tiene adatum.biz como un nombre de dominio comprobado. El asistente no le preguntará para la comprobación adicional debido a que customers.adatum.biz es un subdominio para el nombre ya registrado. Sin embargo, si agrega un FQDN que no se ha comprobado antes, necesitará ir a través del proceso de comprobación. El proceso de comprobación es [se describe a continuación](#add-a-subdomain-to-the-customer-tenant-and-verify-it).

    ![Confirmación de un nombre de dominio comprueba](media/direct-routing-3-sbc-verify-domain.png)

5.  Haga clic en **siguiente**y en la página **Configuración de DNS de actualización** , seleccione **vamos a agregar los registros DNS yo mismo** y haga clic en **siguiente**.
6.  En la siguiente página, desactive todos los valores (a menos que desee usar el nombre de dominio de Exchange, SharePoint o equipos/Skype para la empresa), haga clic en **siguiente**y, a continuación, haga clic en **Finalizar**. Asegúrese de que su nuevo dominio se encuentra en el estado del programa de instalación completado.

    ![Dominios que muestra un estado de la instalación completa](media/direct-routing-14-sbc-setup-complete.png)

### <a name="activate-the-domain-name"></a>Activar el nombre de dominio

Una vez que haya registrado un nombre de dominio, debe activar mediante la adición de al menos un usuario y asignar una dirección SIP con la parte FQDN de la dirección SIP que coincida con el dominio base creado.

*Revise [obtener ayuda con los dominios de Office 365](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) para obtener más información acerca de cómo agregar los usuarios en los inquilinos de Office 365.*

Por ejemplo: test@customers.adatum.biz

![Página de activación de dominio base](media/direct-routing-4-sbc-domain-activation.png)

## <a name="register-a-subdomain-name-in-a-customer-tenant"></a>Registrar un nombre de subdominio en un inquilino del cliente

Debe crear un nombre de subdominio único para cada cliente. En este ejemplo, crearemos un subdominio sbc1.customers.adatum.biz en un inquilino con el woodgrovebank.us de nombre de dominio predeterminado.

**Todas las acciones que aparece a continuación se encuentran en el inquilino del cliente.**

### <a name="ensure-that-you-have-appropriate-rights-in-the-customer-tenant"></a>Asegúrese de que tiene los derechos adecuados en el inquilino del cliente

Sólo se pueden agregar nuevos dominios si ha iniciado sesión el centro de administración de Office 365 como un administrador Global. 

Para validar el rol que tiene, inicie sesión en el centro de administración de Microsoft 365 (https://portal.office.com), vaya a **los usuarios** > **Usuarios activos**y, a continuación, compruebe que dispone de una función de administrador Global. 

Para obtener más información acerca de los roles de administrador y cómo asignar una función de Office 365, vea [roles de administrador acerca de Office 365](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d).

### <a name="add-a-subdomain-to-the-customer-tenant-and-verify-it"></a>Agregar un subdominio para el inquilino del cliente y compruebe
1. En el centro de administración de Microsoft 365, vaya al **programa de instalación** > **dominios** > **Agregue el dominio**.
2. En el cuadro **Escriba un dominio que es propietario** , escriba el FQDN del subdominio para este inquilino. En el ejemplo siguiente, el subdominio es sbc1.customers.adatum.biz.

    ![Adición de un subdominio del cliente](media/direct-routing-5-sbc-add-customer-domain.png)

3. Haga clic en **Siguiente**.
4. El FQDN nunca se ha registrado en el inquilino. En el siguiente paso, debe comprobar el dominio. Seleccione **Agregar un registro TXT en su lugar**. 

    ![Opciones en la página comprobar dominio](media/direct-routing-6-sbc-verify-customer-domain.png)

5. Haga clic en **siguiente**y, tenga en cuenta el valor TXT generado para comprobar el nombre de dominio.

    ![Registros de texto en la página comprobar dominio](media/direct-routing-7-sbc-verify-domain-txt.png)

6. Cree el registro TXT con el valor desde el paso anterior en el proveedor de hospedaje de DNS del operador.

    ![Crear el registro TXT en el proveedor de hospedaje de DNS del operador](media/direct-routing-8-sbc-txt-record.png)

    Para obtener más información, consulte [crear registros DNS en cualquier proveedor de hospedaje de DNS para Office 365](https://support.office.com/article/create-dns-records-at-any-dns-hosting-provider-for-office-365-7b7b075d-79f9-4e37-8a9e-fb60c1d95166).

7. Vaya al centro de administración de Microsoft 365 del cliente y haga clic en **Comprobar**. 
8. En la página siguiente, seleccione **vamos a agregar los registros DNS yo mismo** y haga clic en **siguiente**.

    ![Opciones en la página de configuración de DNS de actualización](media/direct-routing-9-sbc-update-dns.png)

9. En la página **Elija los servicios en línea** , desactive todas las opciones y haga clic en **siguiente**.

    ![La elija la página Servicios en línea](media/direct-routing-10-sbc-choose-services.png)

10. En la página **configuración de actualización de DNS** , haga clic en **Finalizar** .

    ![La página de configuración de DNS de actualización](media/direct-routing-11-sbc-update-dns-finish.png)

11. Asegúrese de que el estado es **completar el programa de instalación**. 
    
    ![Página que muestra el estado de la instalación completa](media/direct-routing-12-sbc-setup-complete.png)

### <a name="activate-the-subdomain-name"></a>Activar el nombre de subdominio

Después de registrar un nombre de dominio, debe activar mediante la adición de al menos un usuario y asignar una dirección SIP con la parte FQDN de la dirección SIP que coincidan con el subdominio creado en el inquilino del cliente.

*Revise [obtener ayuda con los dominios de Office 365](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) para obtener más información acerca de cómo agregar los usuarios en los inquilinos de Office 365.*

Por ejemplo: test@sbc1.customers.adatum.biz

![Activación de la página de subdominio](media/direct-routing-13-sbc-activate-subdomain.png)

### <a name="create-a-trunk-and-provision-users"></a>Crear usuarios de un tronco y aprovisionamiento

> [!NOTE]
> En función de los comentarios que recibimos en el programa de adopción técnica, Microsoft podría cambiar el proceso de creación de troncos en los inquilinos de atención al cliente para simplificar el proceso. Por favor, vea las actualizaciones de documentación de esta página y siga los blogs de la comunidad técnica de Microsoft para obtener más información. 

Crear un tronco en el dominio de cliente mediante el comando New-CSonlinePSTNGateway. El tronco FQDN **debe** coincidir con el subdominio creado para el cliente.

Por ejemplo:

*Nuevo-CSOnlinePSTNGateway – FQDN sbc1.customers.adatum.biz - SipSignallingPort 5068*

Abastecer a los usuarios con los números de teléfono y configuración de enrutamiento de voz.

Para obtener más información sobre el nuevo-CSOnlinePSTNGateway, aprovisionamiento a los usuarios y la configuración de enrutamiento de voz, consulte [Configurar el enrutamiento directo](direct-routing-configure.md).


Consulte las [instrucciones del proveedor SBC](#deploy-and-configure-the-sbc) sobre la configuración de enviar el nombre FQDN de subdominios en el encabezado de contacto.

