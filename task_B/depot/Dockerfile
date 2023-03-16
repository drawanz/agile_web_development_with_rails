
FROM ruby:3.2.1

# Install dependencies
RUN apt-get update && \
    apt-get install -y build-essential libpq-dev postgresql-client

# Set the working directory
WORKDIR /app

# Copy Gemfile and Gemfile.lock
COPY Gemfile Gemfile.lock ./

# Install gems
RUN bundle install --jobs=4 --retry=3

# Copy the rest of the application code
COPY . .

# Expose port 3000 for the Rails server
EXPOSE 3001

# Start the Rails server
CMD ["rails", "server", "-b", "0.0.0.0"]
