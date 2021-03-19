

* 도저히 jpa에 default값이 넣어지지않을때 

```java
    @PrePersist
    public void prePersist() {
        this.verified = this.verified == null ? false : this.verified;
        this.createdAt = this.createdAt == null ? LocalDateTime.now() : this.createdAt;
    }
```


* 시간차를 구할때 
```java
ChronoUnit.MINUTES.between(authority.getCreatedAt(), LocalDateTime.now()
```
