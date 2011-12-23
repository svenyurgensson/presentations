!SLIDE ruby small

# Include our trait into class!
	@@@ ruby
	class User < ActiveRecord::Base

		#
		# Behaviors
		#

		include Traits::GroupOfPeople
		
		#  ... others useful methods ...

	end

!SLIDE

## Для использования Traits::GroupOfPeople 

!SLIDE bullets incremental transition=fade
## наша модель User должна *обеспечивать* методы:

* members
* memberships

!SLIDE

## Иначе будет exception!


!SLIDE ruby small

## Use it in real life:

	@@@ ruby
	user = User.find params[:user_id]
	probably_friend = current_user.add_member user 

и так далее аналогично с remove_member


!SLIDE
И этот наш новый trait мы можем использовать не только с моделью User…

Мы можем использовать его с любыми моделями, обеспечивающими нужный для trait интерфейс


