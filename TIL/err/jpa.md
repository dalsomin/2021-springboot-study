/login HTTP/1.1" 200 1052
2021-03-23 22:34:48,150 15015 [http-nio-8080-exec-4 ] ERROR o.a.c.c.C.[.[.[.[dispatcherServlet] - Servlet.service() for servlet [dispatcherServlet] in context with path [] threw exception [Request processing failed; nested exception is org.springframework.orm.jpa.JpaSystemException: ids for this class must be manually assigned before calling save(): com.innogrid.openstackit.data.entity.authority.AuthorityEntity; nested exception is org.hibernate.id.IdentifierGenerationException: ids for this class must be manually assigned before calling save(): com.innogrid.openstackit.data.entity.authority.AuthorityEntity] with root cause
org.hibernate.id.IdentifierGenerationException: ids for this class must be manually assigned before calling save(): com.innogrid.openstackit.data.entity.authority.AuthorityEntity

entity



---

커스텀 JPA SQL을 할떄는 @Query 를 쓴다. 그런데 ; 있으면 동작안함 !!!!!!!

열받는다....이것때문에......; 
```javascript
  @Query(value="select * from authority a where a.id=:id and a.domain_name=:domainName",nativeQuery = true)
    AuthorityEntity findEmailByIdAndDomainName(@Param("id") String id, @Param("domainName") String domainName);
```
