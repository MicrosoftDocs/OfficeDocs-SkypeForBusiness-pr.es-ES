---
title: Modificar la URL de servicios web en Lync Server 2013
TOCTitle: Modificar la URL de servicios web en Lync Server 2013
ms:assetid: 4cee37c0-3b99-4207-997f-bf4229d760c0
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg520992(v=OCS.15)
ms:contentKeyID: 48275173
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Modificar la URL de servicios web en Lync Server 2013

 

_**Última modificación del tema:** 2015-11-16_

Cuando configura los grupos de servidores front-end y los servidores Standard Edition, tiene la opción de configurar un nombre de dominio completo (FQDN) de la granja de servidores web externa y los puertos asociados. Si no configuró esta dirección URL al ejecutar Asistente para la implementación de Lync Server, es necesario configurar manualmente estos parámetros. Un administrador no suele necesitar modificar estos parámetros, ya que son los puertos predeterminados y recomendados.


> [!NOTE]
> La siguiente pantalla se capturó mientras se configuraba un servidor Standard Edition, por lo que la opción para invalidar el FQDN está desactivada. Esa opción se activa cuando se configura un servidor Enterprise Edition en un grupo de servidores front end.



![Editar configuración de grupo de servicios web](images/Gg520992.fbdf5cc9-479a-463f-bb1d-53575ecdfc9d(OCS.15).jpg "Editar configuración de grupo de servicios web")

## Para configurar servicios web

1.  Inicie sesión en el equipo donde se encuentre instalado el Generador de topologías como miembro del grupo Administradores del dominio y el grupo RTCUniversalServerAdmins.

2.  Inicie el Generador de topologías: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y, después, en **Generador de topologías de Lync Server**.

3.  En Generador de topologías, en el árbol de la consola que hay bajo **Servidores front-end Standard Edition**, **Grupos de servidores front-end Enterprise Edition** y **Grupos de servidores Directory**, seleccione el nombre del grupo de servidores. Haga clic con el botón secundario en el nombre, seleccione **Editar propiedades** y después haga clic en **Servicios web**.

4.  Agregue o edite el **FQDN de servicios web externos** y después haga clic en **Aceptar**.
    
    > [!WARNING]  
	> Si tiene más de un Grupo de servidores front-end o Servidor front-end el FQDN de los servicios web externos deben ser únicos. Por ejemplo, si define el FQDN de los servicios web externos de un Servidor front-end como <strong>pool01.contoso.com</strong>, no puede usar <strong>pool01.contoso.com</strong> para otro Grupo de servidores front-end o Servidor front-end. Si también implementa Directores, el FQDN de los servicios web externos definidos desde cualquier Director o Grupo de directores debe ser único desde cualquier otro Director o Grupo de directores y también desde cualquier Grupo de servidores front-end o Servidor front-end.


5.  Verifique que los puertos de escucha y los puertos publicados están configurados correctamente para su entorno.

6.  Repita estos pasos para todos los servidores Standard Edition, los grupos de servidores front-end y los grupos de servidores de Active Directory de su entorno.

7.  En el árbol de la consola, haga clic en **Lync Server 2013** y después en el panel **Acciones**, haga clic en **Publicar topología**.

A continuación se enumeran algunos requisitos que es necesario conocer a la hora de configurar los puertos de escucha y publicación.

  - Los puertos de escucha que se muestran son los puertos configurados para Internet Information Server (IIS) en cada servidor front-end.

  - Los puertos de escucha internos y externos deben ser diferentes para IIS. En el caso de los puertos de escucha externos, suele tratarse del mismo puerto, ya que uno representa el equilibrador de carga de hardware para el tráfico web interno y otro representa el servidor proxy inverso para el tráfico web externo.

  - Puede reemplazar los servicios web internos en un Grupo de servidores front-end, Director o un Grupo de directores y definir su propio FQDN.
    
    > [!WARNING]  
    > Si decide reemplazar los servicios web internos con un FQDN definido por usted mismo, cada FQDN debe ser único en cualquier Grupo de servidores front-end, Director o Grupo de directores.
    


  - Los puertos publicados deben configurarse como puertos de escucha en el servidor proxy inverso o el equilibrador de carga de hardware.

  - En el caso de un grupo de servidores front-end (que no aparecen en el ejemplo), el FQDN del grupo de servidores SIP interno debe ser diferente al FQDN de servicios web internos, ya que el tráfico web viaja a través del equilibrador de carga de hardware, mientras que el tráfico del grupo de servidores SIP interno viaja a través el equilibrador de carga de DNS. Este requisito se debe cumplir.

  - Una implementación de Lync Server Standard Edition no precisa ni permite que se invalide el FQDN de servicios web internos, ya que dicho servidor no acepta la carga equilibrada.

  - Si tiene un equilibrador de carga de hardware en su entorno que se usa tanto para el tráfico web como para el tráfico SIP interno, Generador de topologías no puede hacer la distinción.
    
    Los FQDN de servicios web se deben diferenciar fácilmente entre sí. Esta medida ayuda a garantizar que la redirección URL conduce a los clientes al servidor adecuado. Por ejemplo, si tiene dos FQDN, sería recomendable que le asignara a uno el nombre, meeting.contoso.com y al otro, conferencing.contoso.com. En teoría, podría tener problemas de redirección si tuviera FQDN con nombres más parecidos entre sí, como, por ejemplo, meet1.contoso.com y meet2.contoso.com.

Los servicios web externos trabajan en combinación con un proxy inverso en la red perimetral. Proporciona a los clientes acceso externo con el uso de dichos servicios web. Los FQDN configurados aquí se envían a los clientes cuando inician sesión y se usan para hacer una conexión HTTPS con el proxy inverso en conexiones remotas. El servidor proxy inverso reenvía el FQDN de servicios web externo a un equilibrador de carga de hardware, o directamente al grupo de servidores. El proxy inverso debe poder resolver el FQDN de servicios web externos en la dirección IP del servidor web interno. El FDQN de servicios web externos debe poder resolverse en Internet.

Si el servidor interno es un Servidor Standard Edition, el FQDN interno es el FQDN de Servidor Standard Edition. Si el servidor interno es un grupo de servidores front-end, el FQDN es una IP virtual (VIP) de equilibrador de carga de hardware que equilibra la carga de la granja de servidores web internos. Es necesario un equilibrador de carga de hardware en un grupo de servidores front-end con varios servidores Enterprise Edition. No se requiere un equilibrador de carga para un servidor Standard Edition o un solo servidor front-end Enterprise Edition.

