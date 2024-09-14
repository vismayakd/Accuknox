Question 1: By default are django signals executed synchronously or asynchronously?
Answer : Django signals are executed synchronously.When a signal is sent, the receiver function is executed immediately in the same time of execution.

def create_user():
    user = User.objects.create(username='testuser')
    print("User created")

@receiver(post_save, sender=User)
def signal_handler(sender, instance, **kwargs):
    print("Signal handler activated")

create_user()

In this code, the signal_handler will execute immediately after the user is saved.

Question 2: Do django signals run in the same thread as the caller?
Answer :Yes, by default, Django signals run in the same thread as the caller.

Question 3: By default do django signals run in the same database transaction as the caller? 
Answer : Yes, Django signals run in the same database transaction as the caller by default.
