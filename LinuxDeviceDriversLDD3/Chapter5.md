Linux Semaphore Implementation

Sema_init
DECLARE_MUTEX(name);
DECLARE_MUTEX_LOCKED(name); // This one keeps the mutex in a locked state.

To initialize at runtime:
Void init_MUTEX(struct semaphore *sem);
Void init_MUTEX_LOCKED(struct semaphore *sem);

Reader/Writer Semaphores

Void init_rwsem(struct rw_semaphore *sem);

Spinlocks

Void spin_lock_init(spinlock_t  *lock);
Void spin_lock(spinlock_t *lock);
Void spin_unlock(spinlock_t *lock);

The core rule that applies to spinlocks is that any code must, while holding a spinlock, be atomic.
 
It cannot sleep.

Cannot relinquish the processor for any reason except to service interrupts (and sometimes not even then).
