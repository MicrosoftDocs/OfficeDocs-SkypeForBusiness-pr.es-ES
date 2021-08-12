---
title: Crear registros DNS para Skype Empresarial Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/15/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 798a663c-0b63-4f75-b0a3-9c553cef8c5f
description: 'Resumen: obtenga información sobre cómo configurar DNS y crear registros DNS para una instalación de Skype Empresarial Server. Descargue una versión de prueba Skype Empresarial Server desde el Centro de evaluación de Microsoft en: https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server .'
ms.openlocfilehash: 94d4f9d0713c2516e466ae25faf05808a56ac103c0571dd151bdc25e2a892f8e
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54307751"
---
# <a name="create-dns-records-for-skype-for-business-server"></a>Crear registros DNS para Skype Empresarial Server
 
**Resumen:** Obtenga información sobre cómo configurar DNS y crear registros DNS para una instalación de Skype Empresarial Server. Descargue una versión de prueba Skype Empresarial Server desde el Centro de evaluación de Microsoft en: [https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server) .
  
Para que Skype Empresarial Server funcione correctamente, debe haber una serie de opciones de configuración del Sistema de nombres de dominio (DNS). Esto es para que los clientes sepan cómo obtener acceso a los servicios y que los servidores se conozcan entre sí. Esta configuración solo debe completarse una vez por implementación, ya que una vez que asigne una entrada DNS, estará disponible en todo el dominio. Puede realizar los pasos del 1 al 5 en cualquier orden. Sin embargo, debe realizar los pasos 6, 7 y 8 en orden y después de los pasos del 1 al 5, tal como se describe en el diagrama. La creación de registros DNS consta del paso 5 de 8. Para obtener más información acerca de la planeación de DNS, vea [Requisitos](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) del entorno para Skype Empresarial Server o Requisitos de servidor [para Skype Empresarial Server 2019](../../../SfBServer2019/plan/system-requirements.md).
  
> [!IMPORTANT]
> Es importante tener en cuenta que este es solo un ejemplo de cómo crear registros DNS en un entorno DNS Windows servidor DNS. Hay muchas otras entradas DNS que son necesarias para Skype Empresarial Server y el procedimiento para crear registros DNS depende del sistema que use para administrar DNS en su organización. Para obtener una lista completa de los requisitos para DNS, vea [Requisitos dns para Skype Empresarial Server](../../plan-your-deployment/network-requirements/dns.md). 
  
![Diagrama de información general](../../media/d2fc733c-6a80-4d17-a02f-93b8c4bfb999.png)
  
## <a name="configure-dns"></a>Configurar DNS

Los registros DNS son necesarios para que Skype Empresarial Server funcionen correctamente y puedan ser accesibles por los usuarios.
  
En este ejemplo se usa un FQDN equilibrado de carga DNS denominado pool.contoso.local. Este grupo consta de tres servidores que ejecutan Skype Empresarial Server Enterprise Edition. Un Standard Edition front-end solo puede contener un único servidor. Al usar Standard Edition, solo usaría el nombre de dominio completo (FQDN) del servidor de Standard Edition único al hacer referencia al rol front-end en lugar de crear un grupo de servidores con carga equilibrada dns, como se muestra en este ejemplo. En este ejemplo sencillo que solo usa el rol front-end se incluyen las entradas DNS de la tabla siguiente. Para planear los requisitos DNS específicos, vea [Requisitos dns para Skype Empresarial Server](../../plan-your-deployment/network-requirements/dns.md). 
  
 
|**Description**|**Tipo de registro**|**Nombre**|**Da como resultado**|**Tipo de equilibrio de carga**|
|:-----|:-----|:-----|:-----|:-----|
|FQDN de servicios web internos  <br/> |A  <br/> |webint.contoso.local  <br/> |VIP para servicios web internos  <br/> |Software y hardware admitidos  <br/> |
|FQDN del grupo de servidores  <br/> |A  <br/> |pool.contoso.local  <br/> |Dirección IP del servidor SFB01  <br/> |DNS  <br/> |
|SFB01 FQDN  <br/> |A  <br/> |SFB01.contoso.local  <br/> |Dirección IP del servidor SFB01  <br/> |DNS  <br/> |
|FQDN del grupo de servidores  <br/> |A  <br/> |pool.contoso.local  <br/> |Dirección IP del servidor SFB02  <br/> |DNS  <br/> |
|SFB02 FQDN  <br/> |A  <br/> |SFB02.contoso.local  <br/> |Dirección IP del servidor SFB02  <br/> |DNS  <br/> |
|FQDN del grupo de servidores  <br/> |A  <br/> |pool.contoso.local  <br/> |Dirección IP del servidor SFB03  <br/> |DNS  <br/> |
|SFB03 FQDN  <br/> |A  <br/> |SFB03.contoso.local  <br/> |Dirección IP del servidor SFB03  <br/> |DNS  <br/> |
|Skype Empresarial Detección automática  <br/> |A  <br/> |lyncdiscoverinternal.contoso.local  <br/> |VIP para servicios web internos  <br/> |Software y hardware admitidos  <br/> |
|Dirección URL sencilla de reunión  <br/> |A  <br/> |meet.contoso.local  <br/> |VIP para servicios web internos  <br/> |Software y hardware admitidos  <br/> |
|Dirección URL sencilla de acceso telefónico  <br/> |A  <br/> |dialin.contoso.local  <br/> |VIP para servicios web internos  <br/> |Software y hardware admitidos  <br/> |
|Url sencilla del programador web  <br/> |A  <br/> |scheduler.contoso.local  <br/> |VIP para servicios web internos  <br/> |Software y hardware admitidos  <br/> |
|Dirección URL sencilla de administración  <br/> |A  <br/> |admin.contoso.local  <br/> |VIP para servicios web internos  <br/> |Software y hardware admitidos  <br/> |
|Detección heredada  <br/> |SRV  <br/> |_sipinternaltls._tcp.contoso.local  <br/> |FQDN del grupo (puerto 5061)  <br/> |N/D  <br/> |
   
### <a name="create-dns-records"></a>Crear registros DNS

1. Inicie sesión en el servidor DNS y abra **el Administrador del servidor**.
    
2. Haga clic en **el menú** desplegable Herramientas y en **DNS.**
    
3. En el árbol de consola del dominio SIP, expanda **Zonas** de búsqueda directa y, a continuación, expanda el dominio SIP en el que Skype Empresarial Server se instalará.
    
4. Haga clic con el botón secundario en el dominio SIP y **seleccione Nuevo host (A o AAAA),** como se muestra en la figura.
    
     ![seleccionar nuevo registro A](../../media/f89c5c1f-b5b7-428c-a6e3-2bcd12e878c3.png)
  
5. En el **cuadro** Nombre, escriba el nombre del registro host (el nombre de dominio se anexará automáticamente).
    
6. En el cuadro Dirección IP , escriba la dirección **IP** del servidor front-end individual y, a continuación, seleccione Crear registro de puntero **asociado (PTR)** o Permitir que cualquier usuario autenticado actualice registros **DNS** con el mismo nombre de propietario, si procede. Tenga en cuenta que esto supone que dns se usa para equilibrar la carga de todo el tráfico con la excepción de los servicios web. En este ejemplo, tenemos tres servidores front-end como se muestra en la tabla.
    
   |**Nombre del servidor**|**Tipo**|**Datos**|
   |:-----|:-----|:-----|
   |SFB01  <br/> |Host (A)  <br/> |10.0.0.5  <br/> |
   |SFB02  <br/> |Host (A)  <br/> |10.0.0.6  <br/> |
   |SFB03  <br/> |Host (A)  <br/> |10.0.0.7  <br/> |
   
7. A continuación, cree las entradas de equilibrio de carga DNS para el grupo. El equilibrio de carga dns permite a DNS enviar solicitudes a los servidores individuales del grupo de servidores mientras se usa el mismo nombre de grupo DNS. Para obtener más información acerca de DNS y equilibrio de carga, vea [Requisitos dns para Skype Empresarial Server](../../plan-your-deployment/network-requirements/dns.md). 
    
    > [!NOTE]
    > La agrupación de varios servidores solo está disponible en Enterprise Edition implementaciones. Si va a implementar un único servidor Enterprise o un servidor Standard Edition, solo debe crear un registro A para el único servidor. 
  
    Por ejemplo, si tuviera un grupo denominado pool.contoso.local y tres servidores front-end, crearía las siguientes entradas DNS:
    
   |**FQDN**|**Tipo**|**Datos**|
   |:-----|:-----|:-----|
   |pool.contoso.local  <br/> |Host (A)  <br/> |10.0.0.5  <br/> |
   |pool.contoso.local  <br/> |Host (A)  <br/> |10.0.0.6  <br/> |
   |pool.contoso.local  <br/> |Host (A)  <br/> |10.0.0.7  <br/> |
   
8. Siga creando registros A para todos los servidores de la implementación planeada. 
    
9. Para crear el registro de servicio (SRV) para la detección heredada, haga clic con el botón secundario en el dominio SIP y seleccione **Otros nuevos registros**.
    
10. En **Seleccione el tipo de registro del recurso**, haga clic en **Ubicación de servicio (SRV)** y, a continuación, haga clic en **Crear registro**.
    
11. Haga clic en **Servicio** y escriba **_sipinternaltls**.
    
12. Haga clic en **Protocolo** y, a continuación, escriba **_tcp**.
    
13. Haga clic en **Número de puerto** y escriba **5061**.
    
14. Haga **clic en Host que ofrece este** servicio y, a continuación, escriba el FQDN del grupo o Standard Edition servidor.
    
     ![Captura de pantalla del nuevo cuadro de diálogo de registro de recursos.](../../media/54b1aac5-a2ec-41fe-90c0-02eaeaa9d1b4.png)
  
15. Haga clic en **Aceptar** y en **Listo**.
    
### <a name="verify-dns-records"></a>Comprobar registros DNS

1. Inicie sesión en un equipo cliente del dominio con una cuenta que sea miembro del grupo Usuarios autenticados o que tenga permisos equivalentes.
    
2. Haga **clic en** Inicio y, a continuación, escriba **cmd** y presione Entrar.
    
3. Escriba **nslookup o \<FQDN of the Front End pool\>** , y presione **\<FQDN of the Standard Edition server or single Enterprise Edition server\>** ENTRAR.
    
4. Continúe comprobando el resto de los registros A de la implementación.
    
5. Si admite clientes heredados y creó el registro SRV, compruebelo escribiendo **set type=srv** en el símbolo del sistema **nslookup** y, a continuación, presione ENTRAR.
    
6. Escriba **_sipinternaltls._tcp. *dominio*** (por ejemplo, _sipinternaltls._tcp.contoso.local) y, a continuación, presione ENTRAR.
    
7. El resultado esperado debe ser similar al que se muestra en la figura. Tenga en cuenta que no todos los registros DNS se muestran en el resultado de ejemplo, pero todos los registros deben comprobarse. 
    
     ![Compruebe la configuración dns.](../../media/4fcaa70f-7717-4939-9652-d2048d6293cc.png)
  

