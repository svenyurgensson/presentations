!SLIDE 
# Немного кода для примера: #

!SLIDE ruby smaller code
	@@@ ruby
	module Traits
	  # Provides common functionality for groups of people where members are
	  module GroupOfPeople

	    def members
	      raise NotImplementedError
	    end

	    def memberships
	      raise NotImplementedError
	    end

	    def administrators
	      self.members.all(:role => :administrator)
	    end

	    def regular_members
	      self.members.all(:role => :regular_member)
	    end

	    def add_member(person, options = {})
	      raise(ArgumentError) unless person
	      return if person.member_of?(self)
	      role = options.fetch(:role, :regular_member)
	      self.memberships.create(:group => self, :person => person, :role => role)
	    end

	    def remove_member(person)
	      raise(ArgumentError) unless person
	      raise(ArgumentError, "#{person.inspect} is not member of #{self.inspect}") unless person.member_of?(self)
	      self.membership_of(person).destroy
	    end

	    # Implementation
	    # ...
	  end
	end # Traits
