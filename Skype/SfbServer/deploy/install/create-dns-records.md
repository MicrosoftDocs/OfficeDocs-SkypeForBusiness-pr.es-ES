---
title: Crear registros DNS para Skype para Business Server
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 2/15/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 798a663c-0b63-4f75-b0a3-9c553cef8c5f
description: 'Resumen: Obtenga información sobre cómo configurar DNS y crear registros DNS para una instalación de Skype para Business Server. Descargue una versión de prueba gratuita de Skype para Business Server desde el Evaluation de Microsoft center en: https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server.'
ms.openlocfilehash: 35e8aecea74cc74cda6ea086a1765642885a091e
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30890686"
---
# <a name="create-dns-records-for-skype-for-business-server"></a>Crear registros DNS para Skype para Business Server
 
**Resumen:** Obtenga información sobre cómo configurar DNS y crear registros DNS para una instalación de Skype para Business Server. Descargue una versión de prueba gratuita de Skype para Business Server desde el Evaluation de Microsoft center en: [https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).
  
Para Skype para Business Server funcione correctamente, debe ser un número de configuración del sistema de nombres de dominio (DNS) en su lugar. Esto es para que los clientes saben cómo tener acceso a los servicios y los servidores se conocen entre sí. Estas opciones de configuración deben realizarse solo una vez por cada implementación debido a que una vez asigne una entrada DNS, que está disponible en todo el dominio. Se pueden realizar los pasos del 1 al 5 en cualquier orden. Sin embargo, debe realizar los pasos 6, 7 y 8 en orden y después de los pasos del 1 al 5, tal como se indica en el diagrama. Creación de registros DNS comprende las tareas paso 5 de 8. Para obtener más información acerca de la planeación de DNS, vea [requisitos de entorno para Skype para Business Server](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) o [requisitos de servidor para Skype para Business Server 2019](../../../SfBServer2019/plan/system-requirements.md).
  
> [!IMPORTANT]
> Conviene aclarar que lo recogido aquí es un ejemplo de cómo crear registros de DNS en un entorno DNS de Windows Server. Hay muchas otras entradas DNS que se requieren para Skype para Business Server y el procedimiento para la creación de registros DNS depende el sistema que se usa para administrar DNS en la organización. Para obtener una lista completa de requisitos de DNS, vea [requisitos de DNS para Skype para Business Server](../../plan-your-deployment/network-requirements/dns.md). 
  
![Diagrama de información general](../../media/d2fc733c-6a80-4d17-a02f-93b8c4bfb999.png)
  
## <a name="configure-dns"></a>Configurar el DNS

Registros DNS son necesarios para Skype para Business Server funcionen correctamente y ser accesible para los usuarios.
  
En este ejemplo usamos un FQDN con equilibrio de carga de DNS llamado pool.contoso.local. Este grupo de servidores consta de tres servidores que ejecutan Skype para Business Server Enterprise Edition. Un servidor front-end Standard Edition puede contener solamente un servidor. Si usáramos Standard Edition, solo podríamos usar el nombre de dominio completo (FQDN) del único servidor Standard Edition al hacer referencia al rol front-end, en vez de crear un grupo de servidores con equilibrio de carga de DNS, como refleja este ejemplo. Este ejemplo sencillo, en el que usamos el rol front-end, incluye las entradas de DNS recogidas en la siguiente tabla. Para planear los requisitos de DNS específicos, vea [requisitos de DNS para Skype para Business Server](../../plan-your-deployment/network-requirements/dns.md). 
  
 
|**Descripción**|**Tipo de registro**|**Nombre.**|**Se resuelve en**|**Tipo de equilibrio de carga**|
|:-----|:-----|:-----|:-----|:-----|
|FQDN de servicios web internos  <br/> |A  <br/> |webint.contoso.local  <br/> |VIP para los servicios web internos  <br/> |Software y hardware compatibles  <br/> |
|FQDN del grupo de servidores  <br/> |A  <br/> |pool.contoso.local  <br/> |Dirección IP del servidor SFB01  <br/> |DNS  <br/> |
|FQDN de SFB01  <br/> |A  <br/> |SFB01.contoso.local  <br/> |Dirección IP del servidor SFB01  <br/> |DNS  <br/> |
|FQDN del grupo de servidores  <br/> |A  <br/> |pool.contoso.local  <br/> |Dirección IP del servidor SFB02  <br/> |DNS  <br/> |
|FQDN de SFB02  <br/> |A  <br/> |SFB02.contoso.local  <br/> |Dirección IP del servidor SFB02  <br/> |DNS  <br/> |
|FQDN del grupo de servidores  <br/> |A  <br/> |pool.contoso.local  <br/> |Dirección IP del servidor SFB03  <br/> |DNS  <br/> |
|FQDN de SFB03  <br/> |A  <br/> |SFB03.contoso.local  <br/> |Dirección IP del servidor SFB03  <br/> |DNS  <br/> |
|Detección automática de Skype Empresarial  <br/> |A  <br/> |lyncdiscoverinternal.contoso.local  <br/> |VIP para los servicios web internos  <br/> |Software y hardware compatibles  <br/> |
|URL sencilla de reunión  <br/> |A  <br/> |meet.contoso.local  <br/> |VIP para los servicios web internos  <br/> |Software y hardware compatibles  <br/> |
|URL sencilla de marcado  <br/> |A  <br/> |dialin.contoso.local  <br/> |VIP para los servicios web internos  <br/> |Software y hardware compatibles  <br/> |
|Dirección URL del Programador web  <br/> |A  <br/> |scheduler.contoso.local  <br/> |VIP para los servicios web internos  <br/> |Software y hardware compatibles  <br/> |
|URL sencilla de administración  <br/> |A  <br/> |admin.contoso.local  <br/> |VIP para los servicios web internos  <br/> |Software y hardware compatibles  <br/> |
|Detección heredada  <br/> |SRV  <br/> |_sipinternaltls._tcp.contoso.local  <br/> |FQDN del grupo de servidores (puerto 5061)  <br/> |N/D  <br/> |
   
### <a name="create-dns-records"></a>Crear registros de DNS

1. Inicie sesión en el servidor DNS y abra el **Administrador de servidores**.
    
2. Haga clic en el menú desplegable **Herramientas** y en **DNS**.
    
3. En el árbol de consola de su dominio SIP, expanda **Zonas de búsqueda directa**y, a continuación, expanda el dominio SIP en el que se va a instalar Skype para Business Server.
    
4. Haga clic con el botón secundario en el dominio SIP y seleccione **Host nuevo (A o AAAA)**, como se muestra en la figura.
    
     ![seleccionando un nuevo informe A](../../media/f89c5c1f-b5b7-428c-a6e3-2bcd12e878c3.png)
  
5. En el cuadro **Nombre**, escriba el nombre del registro de host (el nombre de dominio se anexará automáticamente).
    
6. En el **cuadro Dirección IP**, escriba la dirección IP del servidor front-end individual y, luego, seleccione **Crear registro del puntero (PTR) asociado** o **Permitir a cualquier usuario autenticado actualizar registros de DNS con el mismo nombre de propietario**, si corresponde. Tenga en cuenta que esto presupone que se utiliza DNS para equilibrar la carga de todo el tráfico con excepción de los servicios web. En este ejemplo, se dispone de tres servidores front-end como se muestra en la tabla.
    
   |**Nombre del servidor**|**Tipo**|**Datos**|
   |:-----|:-----|:-----|
   |SFB01  <br/> |Host (A)  <br/> |10.0.0.5  <br/> |
   |SFB02  <br/> |Host (A)  <br/> |10.0.0.6  <br/> |
   |SFB03  <br/> |Host (A)  <br/> |10.0.0.7  <br/> |
   
7. Tras esto, cree las entradas de equilibrio de carga de DNS del grupo de servidores. El equilibrio de carga de DNS permite a DNS enviar solicitudes a servidores individuales del grupo y usar el mismo nombre de grupo de DNS. Para obtener más información acerca de DNS y el equilibrio de carga, vea [requisitos de DNS para Skype para Business Server](../../plan-your-deployment/network-requirements/dns.md). 
    
    > [!NOTE]
    > La opción de agrupar varios servidores solo se encuentra disponible en las implementaciones Enterprise Edition. Si está implementando un único servidor Enterprise o Standard Edition, necesita crear solo un registro A para el único servidor. 
  
    Por ejemplo, si tiene un grupo denominado pool.contoso.local y tres servidores front-end, será necesario crear las siguientes entradas de DNS:
    
   |**FQDN**|**Tipo**|**Datos**|
   |:-----|:-----|:-----|
   |pool.contoso.local  <br/> |Host (A)  <br/> |10.0.0.5  <br/> |
   |pool.contoso.local  <br/> |Host (A)  <br/> |10.0.0.6  <br/> |
   |pool.contoso.local  <br/> |Host (A)  <br/> |10.0.0.7  <br/> |
   
8. Continúe con la creación de los registros A para todos los servidores en la implementación planificada. 
    
9. Para crear el registro del registro de servicios (SRV) para la detección heredada, haga clic con el botón secundario en el dominio SIP y seleccione **Otros registros nuevos**.
    
10. En **Seleccione el tipo de registro del recurso**, haga clic en **Ubicación de servicio (SRV)** y, luego, haga clic en **Crear registro**.
    
11. Haga clic en **Servicio** y escriba **_sipinternaltls**.
    
12. Haga clic en **Protocolo** y, luego, escriba **_tcp**.
    
13. Haga clic en **Número de puerto** y, luego, escriba **5061**.
    
14. Haga clic en **Host que ofrece este servicio** y, luego, escriba el FQDN del grupo de servidores o del servidor Standard Edition.
    
     ![Captura de pantalla del cuadro de diálogo de nuevo registro de recursos.](../../media/54b1aac5-a2ec-41fe-90c0-02eaeaa9d1b4.png)
  
15. Haga clic en **Aceptar** y, luego, haga clic en **Listo**.
    
### <a name="verify-dns-records"></a>Comprobar los registros de DNS

1. Inicie sesión en un equipo cliente del dominio con una cuenta que sea miembro del grupo Usuarios autenticados o que tenga permisos equivalentes.
    
2. Haga clic en **Iniciar**, escriba **cmd** y presione Entrar.
    
3. Tipo de **nslookup \<FQDN del grupo de servidores Front-End\> ** o ** \<FQDN del servidor Standard Edition o servidor Enterprise Edition único\>**, y presione ENTRAR.
    
4. Continúe con la comprobación del resto de los registros A para la implementación.
    
5. Si admite clientes heredados y creó el registro SRV, compruébelo al escribir **set type=srv** en el símbolo del sistema **nslookup** y, luego, presione Entrar.
    
6. Escriba **_sipinternaltls._tcp. *dominio* ** (por ejemplo, _sipinternaltls._tcp.contoso.local), y, a continuación, presione ENTRAR.
    
7. El resultado que obtenga necesita parecerse al de la figura. Recuerde que el resultado de ejemplo no recoge todos los registros de DNS, pero todos ellos necesitan comprobarse. 
    
     ![Verifique las configuraciones DNS.](../../media/4fcaa70f-7717-4939-9652-d2048d6293cc.png)
  

