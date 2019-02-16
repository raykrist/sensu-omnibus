### arm

This is testet on Raspberry Pi with debian stretch.

#### Pre req

1. Install RVM

```sh
curl -sSL https://get.rvm.io | bash
source /etc/profile.d/rvm.sh
```


#### Running a build

1. Clone the sensu-omnibus git repository:

  ```sh
  git clone https://github.com/sensu/sensu-omnibus.git
  ```

2. Change to the sensu-omnibus directory:

  ```sh
  cd sensu-omnibus
  rvm install 2.5
  gem install omnibus
  ```

3. Set `use_git_caching false` in `omnibus.rb`

4. Install gem dependencies:

  ```sh
  bundle install --system
  ```

5. Export version environment variables:

  ```sh
  export SENSU_VERSION=x.y.z
  export BUILD_NUMBER=1
  ```

6. Build Sensu:

  ```sh
  bundle exec omnibus build sensu -l debug
  ```
